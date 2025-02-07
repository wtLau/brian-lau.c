---
title: 'Intro to Authentication with Next JS'
publishDate: '2021-03-29'
excerpt: Authentication is a software layer that provides a method for the system to identify what kind of access could be given, and the use cases may vary.
tags:
  - Web development
seo:
  image:
    src: '/post-3.jpg'
    alt: Beach ocean shore
---

![Beach ocean shore](/post-3.jpg)

Authentication is a software layer that provides a method for the system to identify what kind of access could be given, and the use cases may vary.

On my website, I've used authentication as follows:

- Track who has downloaded my resume
- Track Who signed in
- Log my own private data
- Access to the profile page
- Access to downloadable resume
- Display user name

## What is the problem?

While building my personal website, I thought could enhance the site experience by showing the names of the user/ visitor when they’re signed in. Also, since my resume contains personal information so it would be nice to know who downloaded with their email. And I want to learn about authentication patterns and how to implement them with [Next JS](https://nextjs.org/) apps.

## Implement Process

Since my site doesn't contain any deal-breaking data and developed with a static generated data-fetching approach (Fast Time to Interactive is a priority!). I chose to implement authentication using a static generated authentication pattern.

Initially, I started with [next-iron-session](https://github.com/vvo/next-iron-session) as recommended on [Next Js document](https://nextjs.org/docs/authentication). I thought this would be a good utility library for creating and storing secure cookies, which doesn't require a database, and built specifically for Next Js. As I was experimenting with the [next-iron-session](https://github.com/vvo/next-iron-session), I found that it requires quite a bit of engineering overhead and architectural planning as it is a low-level API for interacting with the browser session storage. For example, I would need to implement operations for login, logout, update, remove manually. While this would be fun to learn and experiment with, it would extend my time in development just for this feature. I believe it would be handy if the app needs control on handling session storage and managing state flows (interacting with Redux). At the moment I only needed something that could handle auth API calls. So, I looked for an alternative solution that could help specifically with my simple requirement.

I found [NextAuth.js](https://next-auth.js.org/)! It is a flexible _easy-to-use_ open-source authentication solution for Next js apps with build-in auth API providers. Super easy to implement (11 lines of code) and support auth operation such as login, log out, etc. using [React Hooks](https://reactjs.org/docs/hooks-intro.html). How sweet! To understand how the library works, it actually exposes REST APIs used by [NextAuth.js](https://next-auth.js.org/) client to call functions internally, and reserved some namespaces within the api/auth routes. I believe this is a great solution for small to medium Next js projects that requires straightforward authentication.

## How secure is it

As far as security goes, I believe both libraries are designed as secure, confidential clients and implements a server-side authentication flow. I have not found any serious security issues listed on both Github. Security would be interesting to expand further and discuss in-depth, but it would a topic for another day!

## Conclusion

That's it! Hopefully, this helps explain my approach to implementing authentication for my [website](https://www.brian-lau.ca).

If you'd like to see a completed example, the entire source code for my website is [open source](https://github.com/wtLau).

Feel free to [send me a message](https://www.brian-lau.ca/contact) if you have any questions or if I've missed anything.

## Reference resources

- [leerob.io/blog/nextjs-authentication](https://leerob.io/blog/nextjs-authentication)
- [nextjs.org/docs/authentication](https://nextjs.org/docs/authentication)
- [next-iron-session](https://github.com/vvo/next-iron-session)
- [NextAuth.js](https://next-auth.js.org/)
