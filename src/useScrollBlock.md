# useScrollBlock

The `useScrollBlock` hook, part of the "hookverse" package, provides a simple way to block and allow scrolling on a webpage. It is designed to be used in React applications.

## Usage

```javascript
import { useScrollBlock } from "hookverse";
```

```javascript
const [blockScroll, allowScroll] = useScrollBlock();
```

## API

### `blockScroll()`

This function blocks scrolling by applying styles to the `html` and `body` elements, preventing scrolling on the page.

### `allowScroll()`

This function allows scrolling by removing the styles applied to the `html` and `body` elements, restoring the normal scrolling behavior.

## Example

```javascript
import React from "react";
import { useScrollBlock } from "hookverse";

const ScrollBlockExample = () => {
  const [blockScroll, allowScroll] = useScrollBlock();

  const handleBlockScroll = () => {
    blockScroll();
  };

  const handleAllowScroll = () => {
    allowScroll();
  };

  return (
    <div>
      <button onClick={handleBlockScroll}>Block Scroll</button>
      <button onClick={handleAllowScroll}>Allow Scroll</button>
    </div>
  );
};

export default ScrollBlockExample;
```

In this example, clicking the "Block Scroll" button will prevent scrolling on the page, and clicking the "Allow Scroll" button will restore the normal scrolling behavior.
