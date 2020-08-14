+++
title = "Automating GitHub File Deletion"
description = "GitHub File Deletion using CSS + AutoHotKey"
tags = [
    "autohotkey",
    "automation",
    "utility",
    "process",
    "css",
    "stylus"
]
featured_image = "/images/delete.jpg"
date = "2020-08-14"
categories = [
    "process",
    "autohotkey",
    "automation",
    "utility",
    "css",
    "stylus"
]
menu = "main"
+++


Quickly delete files with AutoHotKey and some CSS

## 1. Navigate to your GitHub directory where you need to delete files
## 2. Add/Edit CSS of GitHub; using Stylus
```
/* Changes the alert at the top, to position it absolutely */
/* so it doesn't move the page down, from the static setup, */
/* you'll be using with AutoHotKey **/
.flash-full{
    width:100%;
    position:absolute;
    bottom:0;
    right:0;    
}
/* Changes the position of the submit button, removes need to scroll. */
#submit-file{
    box-shadow:0 0 0 4px #2ea44f;
    position:absolute;
    outline:0;
    top:300px;
    right:300px;
}
/* Color the delete button / icon */
#js-repo-pjax-container > div.container-xl.clearfix.new-discussion-timeline.px-3.px-md-4.px-lg-5 > div > div.Box.mt-3.position-relative > div.Box-header.py-2.d-flex.flex-column.flex-shrink-0.flex-md-row.flex-md-items-center > div.d-flex.py-1.py-md-0.flex-auto.flex-order-1.flex-md-order-2.flex-sm-grow-0.flex-justify-between > div:nth-child(2) > form:nth-child(3) > button{box-shadow:inset 0 0 0 20px red, 0 0 0 5px red;}
.octicon-trashcan{color:#fff;}

```

## 3. Set up AutoHotKey Binds
- Bind a key to 'Get Mouse Position & Add Action'
- Bind a key to 'Get Mouse Cursor Position'
- Bind a key to 'Start / Stop Script Execution'

## 4. Set up Static GitHub Directory Browser Window
- Prefer it's own monitor with no obstructions
- Fullscreen, something that never really changes; static setup that AutoHotKey can do easily

## 5. Set up AutoHotKey Positions and Actions
- Use your bind to 'Get Mouse Position & Add Action'(GMPAA) and bind Left Click.
- Use your bind for 'GMPAA' and use it over the file you want deleted. I recommend playing with the delays and I tend to always add 2 Left clicks on the same position just in case the first one doesn't register. 
- Your page load times will vary but I feel like if a delay of 700+ works well.
- This will click on the file position at the top of the list, once you delete a file in that directory, it will select the same position so something that is sort of always maintaining its position is the goal. If you have files you want to keep, just rename them in a way where they stay on the bottom or top of the page. `filename.ext..., zfilename.ext....
- On new page after clicking the file in your Static Browser setup for GitHub;
- Use your bind for 'GMPAA' and use it over The Delete Icon.
- This is where the CSS edit comes into play, use your 'GMPAA' bind on the Commit changes button.
- After Commiting changes, a box should appear in the directory you're redirected to after deleting a file from, saying: File successfully deleted.
- The CSS changes this positioning to put it at the bottom of the page, which helps in automating the rest of the process, as it needs to maintain the static setup. New alerts will just be at the bottom of the page now, without interfering with the positioning on the static page setup.

![Autohotkey setup](/images/autohot.png)

## 6. Make sure that AutoHotKey is doing everything itself by iterating over the parts it needs help with.
- Add delays to compensate for page load times.
- Add two left clicks on each part where you'll need to click, the file from the directory, delete icon/button, and commit changes button.

## 7. Add a repeat count in AutoHotKey, for the number of files in the directory you need deleted. 
- If you have files you don't want deleted in the same directory and you've renamed them at the bottom with zfilename, then be careful you set a good repeat count you can self manage. The point of this is so you can walk away from a large deletion project.
So I recommend you put the files, if you do need to keep them, at the top of the directory. To maintain position of the static setup.

## 8. Walk away
![Autohotkey in action](/images/autohotdely.gif)
