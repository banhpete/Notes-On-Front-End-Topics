# Notes-on-Web-Deb-Mistakes
## October 27th, 2019
### Why do we use the "before"?
Based on my experience so far - we use the pseudo element before to add content before an element. W3 does a great example of showing how "before" works: https://www.w3schools.com/cssref/sel_before.asp.
Another great example of using the "before" pseudo element is here: https://codepen.io/banhpete-the-bold/pen/RwwVwPW. What happened here is that the "before" pseudo element was used to insert a background picture before the body tag instead of inserting the background into the body tag itself. This was done so that we can set an image as a background for the whole page and have it fixed such that when we scroll through the page, we only scroll through the contents of the body tag and not the background (see the codepen). If the background picture was inserted into the body this could not happen because - we need to have the image fixed not the content of the body!
