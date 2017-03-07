# Introduction to the DOM

## Objectives

1. Explain what the DOM is
2. Explain how the DOM came to be

### Back to our html

In this lesson, we will discuss the difference between HTML and the Document Object Model.  Now, we have the ability to see the HTML that constructs any website.  

> Note: We recommend that you use Google Chrome.  (You can download chrome [here](https://www.google.com/chrome/browser/desktop/index.html)).  Chrome has many features that are developer friendly, and because of that it is one of the tools that many developers use.

You can see the HTML for the introduction to Javascript lesson by typing this as the url to google chrome

 `view-source:https://learn.co/tracks/javascript-with-style`

Here is the url we can type into our browser to view the source of www.espn.com:

`view-source:www.espn.com`

You can also view the source of a webpage without typing something new into the url.  

Here's how you do it.  Right click (or two finger click if you have a mac) on your browser.  You should see a dropdown menu.  Towards the bottom, you will see an option to 'view page source'.  Click on that.  

Add Picture Here.

If you examine the newly opened tab, you will see the HTML used to construct the page you were viewing.  So the browser interprets this HTML, along with the styles and Javascript to construct the appearances in the browser.  Notice that this looks very similar to the code we typed in a text editor to render HTML in previous lessons.

<iframe height='265' width="125" scrolling='no' title='js and the web' src='//codepen.io/flatiron/embed/ggyKpb/?height=265&theme-id=0&default-tab=html,result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/flatiron/pen/ggyKpb/'>js and the web</a> by Jeffrey Katz (<a href='http://codepen.io/flatiron'>@flatiron</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

### So then what is the Document Object Model

The best way to describe the Document Object Model, is to see and interact with it.  Let's get to it.

From the learn webpage, look at the menu at the chrome menu at the top of the page, and click on view, then at the very bottom of the view dropdown it says developer.  Upon clicking on developer at the bottom of that you will see Developer Tools.  Click on Developer Tools.  This will pop up the Google Developer Console.  (A quicker way to open up the console in the future is to press command+shift+i).  

When you open the Google Developer Console (or firebug), you will see what looks like HTML.  There are head tags, body tags, divs, etc.  Now from inside the developer console, click on the element that says body, and then click the delete button.  You should see webpage turn white.

Now did you just delete the HTML?  No.  Let's view the page source again.  Right click (or two fingers click on the mac) on the lesson page in the browser and select view page source.  You will see the that the HTML is just as it always was, with a body tag and lots of other elements inside.  

The changes that the developer console caused, and the changes it currently displays are changes in the Document Object Model (which we still didn't explain).  Our webpage now looks blank.  

Let's see evidence of this change a different way.  From inside the developer console, click on the tab that says the word console.  Then at the bottom you will see a cursor.  There, type the word `document`.  What you'll see is that there is a head tag there, but our body tag is gone.  

So by typing in document it looks like our body is gone.  The page displays our body as gone.  However, if we view page source, the HTML is unchanged.

### What is going on?

  * The Document Object Model is a representation of the *current view* of the browser, and can be manipulated without reloading a page.  
  * The HTML is the text in a file first used to render the page.

So the HTML is essentially the starting point of the page's content.  But as we just saw by deleting the body of the page, what is displayed can change.  When we change it, we change the Document Object Model, and that changes the appearance in the browser.  The HTML, however, once loaded on a webpage, does not change.  

### This is still about Javascript right

Ok, so what does this have to do with Javascript?  

Well Javascript allows us to select specific portions of the DOM, and it then allows us to manipulate this Document Object Model, which changes what shows up in a browser window.  

Real fast, let's see this.  Open up the console and type in the following:

  ```javascript
    document.querySelector('header')
    // =>
    // <header class="site-header">
    // </header>
  ```

It retrieves the header tag, which contains the lesson title among other things.  Ok, now let's do something with this header.  Open up the console, and type in the following:

  ```javascript
    document.querySelector('header').remove()
  ```

Take a look at the top of the page again.  The header is gone.  But do you think the HTML has just changed?  Well, no.  As you know, the HTML never changes after it is first rendered.  Instead, we accessed the Document Object Model, altered the model and that altered the appearance of our web page.  

### Summary

We learned a lot in this section.  This is what we learned.  Html is a markup language used to display content in a browser.  When we change the appearance of a webpage, what we are really changing is the Document Object Model, which directly determines the appearance displayed in the browser.  We can view and manipulate the Document Object Model by opening our developer tools, but when we do so the HTML is not changed.  We can also view our Document Object Model by opening the console and typing in the word `document`.  We can select a specific piece of the DOM by using javascript, such as `document.querySelector('header')`, and we can also use javascript to alter our DOM with `document.querySelector('header').remove()`

## Resources

- [CSS Tricks - What is the DOM?](https://css-tricks.com/dom/)
- [MDN - The DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

<p class='util--hide'>View <a href='https://learn.co/lessons/introduction-to-the-dom'>Intro To The DOM</a> on Learn.co and start learning to code for free.</p>
