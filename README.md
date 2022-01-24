# FB9857340 - ios-15-safari-bottom-bug
## When interacting with a text input field at the bottom of a browser tab, Safari's browser background is popping up and sticking around when it should only be visible when actively pulling/scrolling on the screen

I’m running into two related bugs on iOS 15 Safari (including the recent 15.3 release) with a chatbot that lives as an iframe on top of another site. When the user is scrolled to the bottom of the main/parent site’s content, and then taps to open up the text input field in the iframe, the browser background/chrome will pop up and take up visual space between the minimized URL bar and the page contents.

After some research with a basic reproduction, I’ve also determined the some of these issues also happen without an iframe, and just a simple input field toward the bottom of a page. This seems to be an issue with how Safari handles viewport resizing upon keyboard open/close and scrolling to the bottom of the site’s content.

- #1 On a basic site with no CSS or other customizations:
  - When the user is scrolled to the bottom of the page, and then taps to open up a text input field in the html of the parent site, the keyboard opens like expected but the browser background/chrome pops up and take up visual space (~25px of height, 100% width) between the minimized URL bar and the page contents. When the user scrolls back up or closes the keyboard, the browser background/chrome disappears.

- #2 Input inside of an iframe on a basic site:
  - The same experience of #1, but sometimes the browser background/chrome is about twice as tall, and when you close the keyboard (“done”), half of it goes away but the other half of the height is still taken up. On an iframe that takes 100%/100vh of the height of the browser tab, this has the effect of pushing the whole iframe up by the same amount that the browser background/chrome is taking up on the bottom of the page.

These are both disruptive issues to the operation of our chatbot, can you please give the examples in the repo and screen recordings a look and fix this?

Thank you!