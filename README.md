# Revolt CSS snippets
This is a repo containing useful CSS snippets for revolt.chat.

All you have to do to apply them is to **paste them in Settings -> Appearance -> Custom CSS.**

## TODO
- Larger profile modal;

## Wider scrollbar (Firefox)
```css
* {
   scrollbar-width: initial;
}
```

## Hide homescreen actions
![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/d4af37b7-0e52-4aeb-b494-fda2920b1d74)

```css
[class^="_home_"] [class^="_homeScreen_"] [class^="_actions_"] {
  display: none;
}
```

## Remove modal animations
```css
[class^="Container-sc-"], [class^="Base-sc-"], [class^="_settings_"] {
	animation: none !important;
	transition: none !important;
}
```

## Square user avatars
![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/97319ee8-7f9c-4d64-8fec-a159438511a7)

```css
:root {
    --border-radius-user-icon: 3px;
}
```

## Alternative active server indicator
![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/881afbf7-f275-4ca1-88c5-10e3b8ce7d85)

```css
[class^="SwooshWrapper-sc-"] > svg > path:not(:first-child), 
[class^="SwooshWrapper-sc-"] > svg > rect {
    display: none;
}

[class^="SwooshWrapper-sc-"] > svg > path:first-child {
    fill: red;
    /* Fix uneven bubble around the server icon */
    transform: translateX(.8px) scale(.9);
    transform-origin: center;
}
```

## Hide channel icons
```css
div[class^="_item_"] > div[class^="_avatar_"] {
  display: none;
}
```

## Discord style messagebar
![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/ef35b964-b943-4be9-b491-ff399a02ab0d)

```css
[class^="MessageBox__Base-sc-"] {
	margin: 0 1rem 1.4rem 1rem;
	border-radius: 11px;
}
[class^="FilePreview__Container-sc-"],
[class^="TypingIndicator__Base-sc-"], 
[class^="AutoComplete__Base-sc-"], 
[class^="JumpToBottom__Bar-sc-"] {
	margin: 0 1rem;
	border-radius: 11px;
}

[class^="AutoComplete__Base-sc-"] > div{
	border-radius: 11px;
}
```

## Permanent spoiler 
Hide all images and videos by displaying a css spoiler. Hover over it to see it.
On mobile, long press to preview the image, press to view it.

**Known issues:** If you start a video and then stop hovering, the spoiler is going to show regardless and the video keeps playing. 

![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/6fc47ed8-af2d-4201-8177-5d7e07829183)

```css
[class^="Grid-sc-"] {
  position: relative !important;
}

[class^="Grid-sc-"]::before {
  content: "Hidden";
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background: var(--secondary-background);
  font-size: larger;
  transition: .1s;
}

[class^="Grid-sc-"]:hover::before {
  opacity: 0;
  pointer-events: none;
}
```

### Permanent spoiler (Blur)
This is applied only on images.

![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/142832e7-efc8-40c9-a3bc-bc8567c10b17)

```css
[class^="Grid-sc-"] > img[class^="_image_"] {
  filter: blur(40px);
  transition: .2s;
}

[class^="Grid-sc-"] > img[class^="_image_"]:hover {
  filter: blur(0px);
}
```
## Hide Revolt Lounge #General 🤨
**Note**: this will hide every channel with the name "General 🤨" in all servers.
```css
[class^="ServerSidebar__ServerList-sc-"] [aria-label^="General 🤨"] {
  display: none;
}
```

# License
[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

