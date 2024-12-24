---
title: 'Introduction to Testing in React'
publishDate: '2021-09-09'
excerpt: 'A breif high level introduction to testing in React app.'
tags:
  - Testing
seo:
  image:
    src: '/post-5.jpg'
    alt: Dark sphere
---

![Dark sphere](/post-5.jpg)

> The more your tests resemble the way your software is used, the more confidence they can give you. - React Testing Library

## Why Test?

Testing is done to ensure that your app will work as intended for your end users. Having tests will make your app more robust and less error prone. It is a way to verify that the code is doing what the developers intended.

Potential Drawbacks:

- Time consuming and difficult.
- Running tests in CI can cost actual money.
- If done incorrectly, it can give you false positives. Your tests pass, but your app doesn’t function as intended.
- Or false negatives. Your tests fail but your app is functioning as intended.

## Type of Tests

#### End to End

- Automated click-testing of critical paths instead of relying on your users to do it for you.
- Often means combining multiple unit and integration test into one test, hence, E2E
- Minimal mocked or stubbed data
- Usually mount rendering
- e.g: testing the authentication flow, payment flow, checkout flow etc
- Tool: Cypress

#### Integration

- Audit your application holistically and make sure everything works together correctly in harmony.
- Integration tests should mock as little as possible
- Usually done with mounting or rendering a component
- e.g: test if child can update parent's component state
- Tool: Jest, React Testing Library

#### Unit

- Target the critical behavior and functionality of your application.
- Easy to understand and maintain
- Usually shallow rendering
- e.g: a component renderst with the default props
- Tool: Jest, React Testing Library

#### Static

- Use a static type system and a linter to capture basic errors like typos and syntax.
- Tool: Eslint, Prettier, TypeScript

#### Snap Shot

- Create a snapshot of the component and store as `**.snap`
- Test compare previous and current snaps and the test will pass if nothing changed
- Very quick and easy to implement
- Drawbacks: only inform you if the syntax has changed, the failed test doesn't equal to failed functionality (false negative)
- e.g: `__snapshots__/`
- Tool: Jest, React Testing Library

#### Manual

- Click click click
- Lack of confident and time consuming

## What not to test?

- implementation/end user functionality details
  - e.g: Chaning name & variables will break test, false negative
- Third party libraries
  - library is production ready, should be tested on source code
- Many integration tests. No snapshot tests. Few unit tests. Few e to e tests

## Shallow vs mount

Mount actually executes the HTML, CSS, and JS code like a browser would

- A simulated browser
- Doesnt render anything to UI
- Need to unmount or cleanup the component
- Typically used for integration test

Shallow rendering only renders the single component

- does not render child ocmponenets
- able to test component in isolation
- A lot faster than mount tests

### Example: Simple React Component

```jsx
import React from 'react';

const App = () => {
  return (
    <div>
      <ChildComponent />
    </div>
  );
};

const ChildComponent = () => {
  return (
    <div>
      <p> Child components</p>
    </div>
  );
};
```

Shallow Rendering: Note child within `ChildComponent` are not present

```jsx
<App>
  <div>
    <ChildComponent />
  </div>
</App>
```

Mount: Very much like the actual app behavior

```jsx
<App>
  <div>
    <ChildComponent>
      <div>
        <p> Child components</p>
      </div>
    </ChildComponent>
  </div>
</App>
```

## Libraries

React Testing Libray Principles

1. If it relates to rendering components, then it should deal with DOM nodes rather than component instances, and it should not encourage dealing with component instances.
2. It should be generally useful for testing the application components in the way the user would use it. We *are* making some trade-offs here because we're using a computer and often a simulated browser environment, but in general, utilities should encourage tests that use the components the way they're intended to be used.
3. Utility implementations and APIs should be simple and flexible.
