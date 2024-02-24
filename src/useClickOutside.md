# useClickOutside

The `useClickOutside` hook is a custom React hook designed to invoke a callback when a click event occurs outside a specified element.

## Usage

```javascript
import { useClickOutside } from "hookverse";
```

```javascript
const elementRef = useClickOutside(callbackFun);
```

## Parameters

| Name        | Description                                                                 |
| ----------- | --------------------------------------------------------------------------- |
| callbackFun | The callback function to be invoked on click outside the specified element. |

## API

### `elementRef`

A React `RefObject` that should be assigned to the HTML element for which you want to detect clicks outside.

## Example

```javascript
import React, { useRef } from "react";
import { useClickOutside } from "hookverse";

const ClickOutsideExample = () => {
  const handleClickOutside = () => {
    // Your callback function
    console.log("Clicked outside the specified element");
  };

  const elementRef = useClickOutside(handleClickOutside);

  return (
    <div>
      <p>Click outside this element to trigger the callback</p>
      <div ref={elementRef}>{/* Your content */}</div>
    </div>
  );
};

export default ClickOutsideExample;
```

In this example, the `useClickOutside` hook is utilized to detect clicks outside a specified element, triggering the provided callback function.