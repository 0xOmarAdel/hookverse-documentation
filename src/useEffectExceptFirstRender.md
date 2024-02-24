# useEffectExceptFirstRender

The `useEffectExceptFirstRender` hook is a custom React hook designed to execute an effect function after the initial render, excluding the first render.

## Usage

```javascript
import { useEffectExceptFirstRender } from "hookverse";
```

```javascript
useEffectExceptFirstRender(func, deps);
```

## Parameters

| Name | Description                                                                                                                 |
| ---- | --------------------------------------------------------------------------------------------------------------------------- |
| func | The effect function to be executed after the initial render, excluding the first render.                                    |
| deps | An array of dependencies to watch for changes. The effect function will be re-executed if any of these dependencies change. |

## Example

```javascript
import React from "react";
import { useEffectExceptFirstRender } from "hookverse";

const ExampleComponent = () => {
  useEffectExceptFirstRender(
    () => {
      // Your effect function
      console.log("Effect executed except on the first render");
    },
    [
      /* dependencies */
    ]
  );

  // Rest of your component logic

  return <div>{/* Your JSX content */}</div>;
};

export default ExampleComponent;
```

In this example, the effect function will be executed on every render except the first one.
