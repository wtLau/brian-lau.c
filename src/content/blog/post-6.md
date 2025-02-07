---
title: 'Intro to JSX'
publishDate: '2023-02-04'
excerpt: 'If you ever wondering what JSX is, how it is used, and why it was created. You might find this article useful'
isFeatured: true
tags:
  - Web
seo:
  image:
    src: '/post-6.jpg'
    alt: Walking person silhouette
---

![Walking person silhouette](/post-6.jpg)

💡 This was released on [My YouTube Channel](https://www.youtube.com/@lauwangtatbrian), check it out at [Let's talk about JSX](https://www.youtube.com/watch?v=lt9ACV8yzo8&t=38s) 💡

## What's JSX

Spoiler! 👻 JSX is not an airline

## Why JSX

Before introducing JSX, I want you to think about how we can manipulate HTML?

```html
<div>
  <h1>How can this text be changed?</h1>
</div>
```

To be able to dynamically change the content, we’d need some help from JS:

The setup

```js
// Create h1 element in memory
const h1 = document.createElement('hi');
h1.textContent = 'Still unchanged 😢';

// We need to update the DOM
const dom = document.getElementById('app');
dom.append(h1);

// To actually update it:
dom.getElementByTagName('h1')[0].textContent = "It's fianlly changed!";
```

Now its updated. Problem is, no one would write nor read this! We want something that’s Modular, Composable, Reusable.

In modern days, we have very good UX. So okay now think about this:

```jsx
<div>
  <h1>This has to be updated many times</h1>
</div>
```

Sure, you’d want some sort of **tokens** to represent \***\*X\*\*** to dynamically change it . This is where JSX shines!

```jsx
const Title = () => {
  const [count, setCount] = callbackFunction(0); // Hook is beyond the scope of JSX

  return (
    <div>
      <h1>This changed {count} times!</h1>
    </div>
  );
};
```

---

## Facts

✅ JSX is actually a spec

✅ **JSX is an XML-like syntax extension to ECMAScript without any defined semantics**

✅ It's intended to be used by various preprocessors (transpilers) to transform these tokens into standard ECMAScript

❌  **It's NOT a proposal to incorporate JSX into the ECMAScript spec itself**

❌  It's **NOT** intended to be implemented by engines or browsers

---

## And More …

- Generic but well defined syntax enable parsers tools like:
  - Eslint, TypeScript, Tailwind, Prettier, and syntax highlighters etc
- Could co-exist with with other lib with a thin extension wrapper
- Could write JS logic in side the templates
- JSX is designed as an ECMAScript feature and the similarity to XML is only for familiarity
- Works for Server-Side-Render(SSR)


## Trade-off

- Embedding a new syntax in an existing language is not the plan. Therefore, it will always require a transpiler to have it work.

## Use Your Creativity 🧠

How would you twist JSX to create something that solve your problem? For example

- File extension
- Style classes
- Reference
- Reactivity
- Virtual DOM
- Reconciliation
- Control flow
- Sever rendering
- the list goes on… :)

## Addiontional Readings:

If you find this interesting, here are some of the readings I went through and found interesting!

[JSX](https://facebook.github.io/jsx/)

[Demystifying SolidJS' JSX](https://www.youtube.com/watch?v=5du6jBlryIc&ab_channel=RyanCarniato)

[Documentation - JSX](https://www.typescriptlang.org/docs/handbook/jsx.html)

[RF21 - Ryan Carniato - SolidJS - Reactive JSX](https://www.youtube.com/watch?v=2iK9zzhSKo4&ab_channel=ReactFinland)

[Introducing JSX - React](https://reactjs.org/docs/introducing-jsx.html)

[react-engine vs other template engines](https://stackoverflow.com/questions/32619168/react-engine-vs-other-template-engines)

[JSX (JavaScript) - Wikipedia](<https://en.wikipedia.org/wiki/JSX_(JavaScript)>)

[https://github.com/airbnb/javascript/pull/985](https://github.com/airbnb/javascript/pull/985)

[React/JSX as a server-side templating language](https://kentcdodds.com/blog/react-jsx-as-a-server-side-templating-language)

---

If you'd like to see a completed example, the entire source code for my website is [open source](https://github.com/wtLau).

Feel free to [send me a message](https://www.brian-lau.ca/contact) if you have any questions or if I've missed anything.
