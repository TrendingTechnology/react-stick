# react-stick

[![CircleCI][build-badge]][build]
[![codecov][codecov-badge]][codecov]
[![npm package][npm-badge]][npm]
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

_Stick_ is a component that allows to attach an absolutely positioned node to a statically
positioned anchor element. Per default, the node will be rendered in a portal as a direct
child of the `body` element.

```bash
npm install --save react-stick
```

```javascript
import Stick from 'react-stick'

<Stick node={<p>The stick node</p>} position="bottom center" align="top center">
  <p>The anchor node</p>
</Stick>
```

## Props

| prop name                | type                                                                                                                                                                                                                                                                                                                                                              | description                                                                                                                                                                                                                                                                                                                       |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `children`               | node                                                                                                                                                                                                                                                                                                                                                              | The anchor element                                                                                                                                                                                                                                                                                                                |
| `node`                   | node                                                                                                                                                                                                                                                                                                                                                              | The node to stick to the anchor element                                                                                                                                                                                                                                                                                           |
| `position`               | one of: `"bottom left"`, `"bottom left"`, `"bottom center"`,`"bottom center"`, `"bottom right"`, `"bottom right"`, `"middle left"`, `"middle left"`, `"middle center"`, `"middle center"`, `"middle right"`, `"middle right"`, `"top left"`, `"top left"`, `"top center"`, `"top center"`, `"top right"`, `"top right"` (default value: `"bottom left"`)          | The reference point on the anchor element at which to position the stick node                                                                                                                                                                                                                                                     |
| `align`                  | one of: `"bottom left"`, `"bottom left"`, `"bottom center"`,`"bottom center"`, `"bottom right"`, `"bottom right"`, `"middle left"`, `"middle left"`, `"middle center"`, `"middle center"`, `"middle right"`, `"middle right"`, `"top left"`, `"top left"`, `"top center"`, `"top center"`, `"top right"`, `"top right"` (default value depends on the `position`) | The alignment of the stick node. You can also think of this as the reference point on the stick node which is placed on the `position` reference point of the anchor node. For example `position="top left" align="bottom right"` means "put the bottom right point of the stick not onto the top left point of the anchor node". |
| `sameWidth`              | boolean                                                                                                                                                                                                                                                                                                                                                           | If set to `true`, the container of the stick node will have the same width as the anchor node. This enforces a maximum width on the content of the stick node.                                                                                                                                                                    |
| `onClickOutside`         | function: (event: Event) => void                                                                                                                                                                                                                                                                                                                                  | A handler that is called on every click on any element outside of the anchor element and the stick node.                                                                                                                                                                                                                          |
| `inline`                 | boolean                                                                                                                                                                                                                                                                                                                                                           | If set to `true`, the stick node will not be rendered detached but inside the same container,as the anchor node.                                                                                                                                                                                                                  |
| `updateOnAnimationFrame` | boolean                                                                                                                                                                                                                                                                                                                                                           | If set to `true`, will update the stick node position on every animation frame. Per default, it will only update on idle callback.                                                                                                                                                                                                |

[build-badge]: https://circleci.com/gh/signavio/react-stick/tree/master.svg?style=shield&circle-token=:circle-token
[build]: https://circleci.com/gh/signavio/react-stick/tree/master
[npm-badge]: https://img.shields.io/npm/v/react-stick.svg
[npm]: https://www.npmjs.org/package/react-stick
[codecov-badge]: https://img.shields.io/codecov/c/github/signavio/react-stick.svg
[codecov]: https://codecov.io/gh/signavio/react-stick
