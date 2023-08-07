# React-Double Scrollbar

## Ambient Note

This is a forked version of this library. The only change is the last commit that makes sure the `.map` file is shipped. We need this because we want to ship source maps to Sentry to help us debug issues. Without this we can't build the app because of the way CRA is setup.

This library is no longer maintained this issue has a PR opened up for it but because no one is maintaining it the PR can't be merged.

We are using `@material-table/core` in some of our legacy features. We should remove that library because they are knowlingly using this unmaintained library and refuse to fix it even though this library is less than 100 lines.

We can get rid of this library when we either:

1. Get rid of the `@material-table/core` dependency we can delete this repo and remove the override from the `product` repo.
2. Migrate the `product` repo away from CRA so we can ignore the source maps issue from this library and remove the override

---

Adds a horizontal scrollbar to the top of an element.

## Usage

Example in a React.Component render method:

```javascript
render() {
    return (
      <div>
        <DoubleScrollbar>
          <table>...</table>
        </DoubleScrollbar>
      </div>
    );
  }
```

## Installation

The easiest way to use React-Double Scrollbar is to install it from NPM and include it in your own build.

```javascript
npm install react-double-scrollbar --save
```

You can also use the standalone build by including `dist/DoubleScrollbar.js` in your page.

# License

MIT

# Change log

v0.0.15

- Recalculate the width of the children in componentDidUpdate and if the width has changed update the width of the top scrollbar div.

v0.0.11

- Add onresize to update the scrollbar when the window size changes

v0.0.10

- Dependency fix, added peerDependency and allow for react 0.14.7 or newer

v0.0.9

- Added tests and documentation

# Contributing

All help is appreciated. To contribute please create a branch, make changes, add or update tests then create a pull request.

# Development

Clone repo then run

`npm install`

To build run

`npm run build`

To test

`npm test`

Test in watch mode

`npm test -- --watch`

# To create and publish a new version

Make sure to update version in package.json

To create a new tag run

`git tag <new version>`

`git push origin --tags`

To publish to npm

`npm publish`
