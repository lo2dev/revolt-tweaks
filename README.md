# Revolt Tweaks
This is a repo containing useful tweaks for revolt.chat.

To apply them, **paste them in Settings -> Appearance -> Custom CSS.**

## Wider scrollbar (Firefox)
```css
/* -- Wider scrollbar (Firefox) -- */
* {
   scrollbar-width: initial;
}
```

## Wider scrollbar (Desktop/Chrome/Edge/etc)
```css
/* -- Wider scrollbar (Desktop/Chrome/Edge/etc) -- */
*::-webkit-scrollbar {
  width: 15px;
}

*::-webkit-scrollbar-track {
  background: var(--primary-background); /* color of the tracking area */
}

*::-webkit-scrollbar-thumb {
  background-color: var(--accent); /* color of the scroll thumb */
  border-radius: 20px; /* roundness of the scroll thumb */
}
```

## Hide homescreen actions
![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/d4af37b7-0e52-4aeb-b494-fda2920b1d74)

```css
/* -- Hide homescreen actions -- */
[class^="_home_"] [class^="_homeScreen_"] [class^="_actions_"] {
  display: none;
}
```

## Remove modal animations
```css
/* -- Remove modal animations -- */
[class^="Container-sc-"], [class^="Base-sc-"], [class^="_settings_"] {
	animation: none !important;
	transition: none !important;
}
```

## Square user avatars
![image](https://github.com/lo-kiss/revolt-tweaks/assets/26941050/65e74c33-5fcc-486a-b965-44ecdfb615c4)

```css
/* -- Square user avatars -- */
/* !! :root should be moved at the top of the theme !! */
:root {
	--border-radius-user-icon: 3px;
}
[class^="TypingIndicator__Base-sc-"] > div > [class^="avatars"] > img {
	border-radius: 3px;
}

```

## Square server icons (and more)
![image](https://github.com/lo-kiss/revolt-tweaks/assets/60184397/7acd9aff-5d0e-43df-9325-487b53c0e6af)

```css
/* -- Square server icons (and more) -- */
[class^="Image-sc-"],
[class^="IconBase__ImageIconBase-sc-"] {
	border-radius: 3px;
}
```

## Wide emoji
![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/f8820fae-5599-4ada-a72d-973c225db9e8)

**Credit:** amycatgirl
```css
/* -- Wide emoji -- */
.emoji {
  width: unset !important;
  max-width: 100%;
}
```

## Rounded message highlight
![image](https://github.com/lo-kiss/revolt-tweaks/assets/115636509/ee7aa5b5-f4c4-4c86-bb13-6cf6b365c810)
```css
/* -- Rounded message highlight -- */
[class^="MessageBase"] {
  border-radius: 8px;
  margin-left: .3rem;
  margin-right: .3rem;
}
```

## Blurred server sidebar
![image](https://github.com/lo-kiss/revolt-tweaks/assets/60184397/f4c3ab99-3694-4ffd-bf0a-aa63824a37ed)
![image](https://github.com/lo-kiss/revolt-tweaks/assets/60184397/835da04f-6437-411e-81c3-b47b92258e30)

```css
/* -- Blurred server sidebar -- */
[class^="SidebarBase-sc-"] > [class^="Base-sc-"] {
	filter: blur(7px);
	transition: 1s cubic-bezier(0.33, 1, 0.68, 1);
}

[class^="SidebarBase-sc-"] > [class^="Base-sc-"]:hover {
	filter: blur(0px);
	transition: 0.4s cubic-bezier(0.33, 1, 0.68, 1);
}
```

## Alternative active server indicator
![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/881afbf7-f275-4ca1-88c5-10e3b8ce7d85)
> [!NOTE]  
> Incompatible with Square server icons
```css
/* -- Alternative active server indicator -- */
[class^="SwooshWrapper-sc-"] > svg > path:not(:first-child), 
[class^="SwooshWrapper-sc-"] > svg > rect {
    display: none;
}

[class^="SwooshWrapper-sc-"] > svg > path:first-child {
	fill: var(--accent);
	/* Fix uneven bubble around the server icon */
	transform: translateX(.8px) scale(.9);
	transform-origin: center;
}
```

## Consistent server header side
![image](https://github.com/lo-kiss/revolt-tweaks/assets/60184397/f0b78985-355a-4ad9-a662-bcdf26421a60)
![image](https://github.com/lo-kiss/revolt-tweaks/assets/60184397/0d7b7525-c8d5-4b88-90ba-7835e720e684)

```css
/* -- Consistent server header side -- */
[class^="ServerHeader__ServerBanner-sc-"] {
	height: 48px;
}
```

## Auto-hiding channels list
Automatically hides the channels sidebar until hovered over.
```css
/* -- Auto-hiding channels list -- */
[class^="ServerSidebar__ServerBase-sc-"]:hover {
	width: 232px;
	transition: 0.4s cubic-bezier(0.33, 1, 0.68, 1);
}

[class^="ServerSidebar__ServerBase"] {
	width: 50px;
	transition: 0.4s cubic-bezier(0.65, 0, 0.35, 1);
}
```

## Auto-hiding members list
Automatically hides the members sidebar until hovered over.
```css
/* -- Auto-hiding members list -- */
[class^="SidebarBase-sc-"]:nth-child(2):hover {
	width: 232px;
	transition: 0.4s cubic-bezier(0.33, 1, 0.68, 1);
}

[class^="SidebarBase-sc-"]:nth-child(2) {
	width: 54px;
	transition: 0.4s cubic-bezier(0.65, 0, 0.35, 1);
}
```

## Hide channel icons
```css
/* -- Hide channel icons -- */
div[class^="_item_"] > div[class^="_avatar_"] {
	display: none;
}
```

## Discord style messagebar
![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/ef35b964-b943-4be9-b491-ff399a02ab0d)

```css
/* -- Discord style messagebar -- */
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

## Message bubbles
Displays messages in a bubble.
![image](https://github.com/lo-kiss/revolt-tweaks/assets/60184397/16deeba2-83a1-4267-972e-41d4d38a4254)

```css
/* -- Message bubbles -- */
[class^="MessageBase__MessageContent-sc-"] {
	background-color: var(--tertiary-background);
	border-radius: 18px;
	padding: 10px 13px 10px 13px;
	flex-grow: 0;
}
```

## Hide blocked messages
```css
/* -- Hide blocked messages -- */
[class^="MessageRenderer__BlockedMessage-sc-"] {
	display: none;
}
```

## Permanent spoiler 
Hide all images and videos by displaying a css spoiler. Hover over it to see it.
On mobile, long press to preview the image, press to view it.

> [!NOTE]
If you start a video and then stop hovering, the spoiler is going to show regardless and the video keeps playing. 

![image](https://github.com/lo-kiss/revolt-css-snippets/assets/115636509/6fc47ed8-af2d-4201-8177-5d7e07829183)

```css
/* -- Permanent spoiler -- */
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
/* -- Permanent spoiler (Blur) -- */
[class^="Grid-sc-"] > img[class^="_image_"] {
  filter: blur(40px);
  transition: .2s;
}

[class^="Grid-sc-"] > img[class^="_image_"]:hover {
  filter: blur(0px);
}
```

## Alternative user popup (Flawed)
**Note:** This effects every popup, including images, warnings, errors, etc.
![image](https://github.com/lo-kiss/revolt-tweaks/assets/60184397/b1945041-d7fb-4ec7-837b-f9df12813dda)

```css
/* -- Alternative user popup (Flawed) -- */
[class^="Base-sc-1d"] {
	background: rgba(0, 0, 0, 0.4);
}
    
[class^="Container-sc-1d"] {
	position: fixed;
	bottom: -1.5rem;
}
```

## Use foreground colour on server unread indicator

```css
a[href^="/server/"] svg > circle {
	fill: var(--foreground) !important;
}
```

## Material design 3 styled components (incomplete)
```css
[class^="MessageBox__Base"] {
  padding: 3px;
  margin: 5px 10px 10px 10px;

  border-radius: 15px;
}

[class^="AutoComplete__Base"] div {
  background: transparent;
  padding: 3px;
}

[class^="AutoComplete__Base"] button {
  background-color: var(--secondary-background);
  padding: 10px;
  transition: border-radius .1s cubic-bezier(.62,.07,.48,.97);
}

[class^="AutoComplete__Base"] button.active {
  background-color: var(--accent);
  color: var(--background);
}

[class^="AutoComplete__Base"] :not(button:first-of-type, button:last-of-type), [class^="AutoComplete__Base"] button:only-of-type {
  border-radius: 10px !important;
}

[class^="ReplyBar__Base"], [class^="ReplyBar__Base"]:only-of-type {
  border-radius: 5px;
  margin: 5px 10px;
}

[class^="AutoComplete__Base"] button:first-of-type {
  border-radius: 20px 20px 10px 10px;
}

[class^="ReplyBar__Base"]:first-of-type {
  border-radius: 15px 15px 5px 5px;
}

[class^="AutoComplete__Base"] button:last-of-type {
  border-radius: 10px 10px 20px 20px;
}

[class^="ReplyBar__Base"]:last-of-type {
  border-radius: 5px 5px 15px 15px;
}

[class^="ReplyBar__Base"], [class^="ReplyBar__Base"]:only-of-type {
  border-radius: 5px;
  margin: 5px 10px;
}

/** Attachment carousel */

[class^="FilePreview__Container"] {
 margin: 5px 10px;

 border-radius: 10px;
}

span.fn { display: none; }
span.size { text-align: start !important; margin-left: 3px; }

/** Reactions (Might change classes after next commit) */
.sc-jSgvzq {
  border-radius: 30px;
  padding: 10px;
  border: 1px solid var(--primary-header);
}

/** active */
.fDfxAc {
  background-color: var(--accent) !important;
  color: var(--background) !important;
  border: none !important;
  font-weight: 600;
}

/** Messages (QOL) */

.sc-jJEKmz {
  margin-bottom: 3px;
}

pre[class^="sc"] {
  position: relative;
  border-radius: 10px;
  border: 1px solid var(--tertiary-background);
}

pre[class^="sc"] div[class^="sc"] a {
  border: 1px solid var(--tertiary-background);
  color: var(--foreground);
  background: transparent;
  box-shadow: unset;
  border-radius: 5px;
}

pre[class^="sc"] div[class^="sc"] {
  position: absolute;
  top: 7px;
  right: 7px;
}

/** Context Menu */

#Menu {
  padding: unset;
  border-radius: 5px;
  backdrop-filter: unset;
  background-color: var(--message-box);
}

#Menu [class^="LineDivider"] {
  background-color: var(--tertiary-background);
  width: 100%;
}

#Menu span {
  border-radius: unset;
  margin: 0;
  padding: 5px;
}

#Menu > span:hover {
  background-color: rgba(var(--accent-rgb),max(var(--min-opacity),.20))
}

/** Server Info/Channel Sidebar */

[class^="ServerSidebar__ServerList"] summary {
  padding: 5px;
  border-radius: 30px;
  margin-bottom: 5px;
}

[class^="ServerSidebar__ServerList"] summary .padding {
  display: flex;
  flex-flow: row-reverse;
  width: 100%;
}

[class^="ServerSidebar__ServerList"] summary .padding svg {
  margin-left: auto;
}

[class^="ServerSidebar__ServerList"] a {
  display: inline-block;
  margin: 1px 5px;
  height: 3rem;
  width: 100%;
  max-width: calc(100% - 10px);
}

[class^="ServerSidebar__ServerList"] [class^="_item_"] {
  padding: 20px;
  border-radius: 30px;
}

[class^="ServerSidebar__ServerList"] [class^="_item_"][data-active] {
  background-color: var(--accent);
  color: var(--background);
}

[class^="ServerSidebar__ServerList"] details [class^="_item_"] {
  margin-left: 10px;
}

[class^="ServerSidebar__ServerList"] details[open] summary {
  background-color: var(--hover);
}

/** Profile modal **/

div[type="user_profile"] [class^="_header_"] {
  border-radius: 15px 15px 0 0;
}

div[type="user_profile"] [class^="_content_"] {
  border-radius: 0 0 15px 15px;
}

/** Server List **/

a[href="/settings"] div svg .gafLvO {
  border-radius: 5px;
  background-color: var(--accent);
  color: var(--background);
}

/** Tooltips **/

.tippy-arrow {
  display: none;
}

.tippy-box {
  border-radius: 10px;
  padding: 5px;
  background-color: var(--primary-background);
  box-shadow: 0 0 5px 5px #00000033;
}
```

![image](https://github.com/amycatgirl/revolt-tweaks/assets/138383945/4e6a4244-72f1-4286-be40-4c9fc14c9f8b)
![image](https://github.com/amycatgirl/revolt-tweaks/assets/138383945/f8b147cd-9af4-4f48-a73e-f2ae80a1e439)
![Screenshot_20240125_162646](https://github.com/amycatgirl/revolt-tweaks/assets/138383945/bebb5d32-cf25-4279-b8fa-30a1208f1351)



# License
[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

