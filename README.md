# Introduction to the DOM

## Objectives

1. Explain what the DOM is
2. Explain how the DOM came to be

## What does "DOM" stand for?

Document Object Model

## Is the DOM just my HTML?

No. The DOM is the parsed version of your HTML, meaning that it is a bunch of live nodes that expose various ways of interacting with them.

## How do I interact with the DOM?

You use JavaScript!

## Can the DOM change?

You betcha. JavaScript can update just about any aspect of the DOM, including adding and removing elements, modifying interactions, and even changing the entire page.

## Okay, but so what is the DOM really?

[MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction) provides as succinct an answer as anyone could:

> A Web page is a document. This document can be either displayed in the browser window, or as the HTML source. But it is the same document in both cases. The Document Object Model (DOM) provides another way to represent, store and manipulate that same document. The DOM is a fully object-oriented representation of the web page, and it can be modified with a scripting language such as JavaScript.

Essentially, the DOM structures our HTML as _document_, with which we can then interact. Most of the interactions happen through APIs exposed by DOM nodes, which are the elements on the page.

## How is the DOM structured?

The DOM is essentially one big nested object.

(!!!)

Hold up. Like a JavaScript object?

Basically. You can interact with it like you would just about any ol' JS object, except that it has a few special properties. This means that we can traverse it starting at a known root (usually the `body`, which we can access at `document.body`) all the way down to the most deeply nested element.

## What does the DOM look like?

Well, in its most presentable form, it looks like the web page that we're on right now. More abstractly, it's a bunch of tags (delimited by `<` and `>`), and so might look something like:

``` html
<html>
<head>
  <title>Hello!</title>
</head>
<body>
  <div>
    <p>Hello, world!</p>
  </div>
</body>
</html>
```

Notice that our very first tag is `<html>` — "HTML" stands for HyperText Markup Language, and it's the language that these tags are written in.

Then we have a `<head>` tag. Anything that appears between `<head>` and `</head>` (the `/` tells us that it's a closing element) won't show up directly on the page. `<title>Hello!</title>` sets the title of the page to "Hello!" (you can see the title of any page at the top of that page's tab).

Then we have `<body>`, which is closed with `</body>`. Anything that appears here will show up on the page — in this case, we have a `<div>`, which is the main __div__iding element on the page (for setting off different parts of the document) and a `<p>` tag, which stands for paragraph (and contains text).

Finally, we close the document with `</html>`.

## Where's the JavaScript?

Well, that's the thing. You can add JavaScript directly between the `<body>` tags. The DOM gets parsed from top to bottom, so it's best to write all of our JavaScript at the bottom of the page:

```html
<html>
<head>
  <title>Hello!</title>
</head>
<body>
  <div>
    <p>Hello, world!</p>
  </div>
  <script>
    alert('hi there!')
  </script>
</body>
</html>
```

Open up a text file (we've provided an empty `index.html` in this repo for you), save the file as something like `index.html`, and open it in any web browser, you should see an alert that says, "hi there!".

## I thought you said we could manipulate the DOM with JavaScript?

And I wasn't kidding! Change the above to the following:


```html
<html>
<head>
  <title>Hello!</title>
</head>
<body>
  <div>
    <p>Hello, world!</p>
  </div>
  <script>
    document.getElementsByTagName('p')[0].innerText = "Sup?"
  </script>
</body>
</html>
```

Save it and load it up in a web page — see that? The page no longer says, "Hello, world!" but instead says, "Sup?"

We accomplished this with `document.getElementsByTagName('p')`, which gets all of the `<p>` tags on the page as an [HTMLCollection](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection). We take the first one (HTMLCollections work a lot like arrays, it turns out), and set its `innerText` property to `"Sup?"`.

Can you change the above so that it says something awesome? Maybe make the greeting say "Awesome!"?

## Resources

- [CSS Tricks - What is the DOM?](https://css-tricks.com/dom/)
- [MDN - The DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction) <-- If you read nothing else, read this!
- [html](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
- [head](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head)
- [title](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
- [body](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)
- [div](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
- [p](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
- [script](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

<p class='util--hide'>View <a href='https://learn.co/lessons/introduction-to-the-dom'>Intro To The DOM</a> on Learn.co and start learning to code for free.</p>
