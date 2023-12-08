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

**Known issues:** If you start a video and then stop hovering, the spoiler is going to show regardless and the video keeps playing. 

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

# License
[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

