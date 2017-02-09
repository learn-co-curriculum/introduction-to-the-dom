# Introduction to the DOM

## Objectives

1. Explain what the DOM is
2. Explain how the DOM came to be

### Back to our html

Ok, so open up espn.html file again.  When you open the google developer console (or firebug), you will see what looks like html.  There are head tags, body tags, divs, etc.  Now click on the body tag such that it turns blue.  Then click the delete button.  You should see the entire webpage turn white.  Now did you just delete the html?  No, instead what you did was manipulate the DOM.  Right click (or two fingers click on the mac) on the espn page in the browser and select view page source.  You will see the that the html is just as it always was, with a body tag and lots of stuff inside.

However in the developer console the DOM is changed.  Our webpage now looks blank.  Go to the console in Google Developer Tools, and type in the word `document`.  If you click on the arrow that is returned, you will see the same thing.  There is now, inside the html the tag of head, but as we deleted it, body is removed.  

So what's the difference here?

  * DOM is a model of a document with an associated API for manipulating it.  It is a representation of the current view of the browser, and can be manipulated without reloading a page.  
  * The html is the text in a file first used to render the page.

So the html is essentially the starting point of the page's content.  But as we just saw by deleting the body of the page, what is displayed can change.  When we change it, we change the Document Object Model, and that changes the appearance in the browser.  

### This is still about Javascript right

Ok, so what does this have to do with Javascript?  Well Javascript allows us to select specific portions of the DOM, and it then allows us to manipulate this Document Object Model, which changes what shows up in a browser window.  

Real fast, let's see this.  Open up the console and type in the following:

  ```javascript
    document.querySelector('h1')
    // => <h1>
      // <a href="/" name="&amp;lpos=sitenavdefault&amp;lid=sitenav_main-logo">ESPN</a>
    // </h1>
  ```

It retrieves the h1 tag, which contains the ESPN logo.  Ok, now let's do something with this logo.  Open up the console, and type in the following:

  ```javascript
    document.querySelector('h1').remove()
  ```

Take a look at the ESPN logo again.  It's gone.  But do you think the HTML has just changed?  Well, no.  As you know, the HTML never changes after it is first rendered.  Instead, we accessed the Document Object Model, altered the model and that altered the appearance of our web page.  

### Summary

We learned a lot in this section.  This is what we learned.  Html is a markup language used to display content in a browser.  When we change the appearance of a webpage, what we are really changing is the Document Object Model, which always reflects the appearance displayed in the browser.  We can view and manipulate the Document Object Model by opening our developer tools, but when we do so the HTML is not changed.  We can also view our Document Object Model by opening the console and typing in the word `document`.  We can select a specific piece of the DOM by using javascript, such as `document.querySelector('h1')`, and we can also use javascript to alter our DOM with `document.querySelector('h1').remove()`

## Resources

- [CSS Tricks - What is the DOM?](https://css-tricks.com/dom/)
- [MDN - The DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

<p class='util--hide'>View <a href='https://learn.co/lessons/introduction-to-the-dom'>Intro To The DOM</a> on Learn.co and start learning to code for free.</p>
