The `useAxios` hook is a custom React hook designed to simplify HTTP requests using Axios with React functional components.

## Usage

```javascript
import { useAxios } from "hookverse";
```

```javascript
const { runAxios, data, loading, isExecuting, error } = useAxios({
  url: "https://api.example.com/data",
  method: "GET",
  headers: {
    "Content-Type": "application/json",
    // Additional headers if needed
  },
  body: {
    // Request body if applicable
  },
  searchParams: "param1=value1&param2=value2",
});
```

## API

### `runAxios`

A function to execute the Axios request.

### `data`

The response data from the API request.

### `loading`

A boolean indicating if the data is currently being fetched.

### `isExecuting`

A boolean indicating if the Axios request is currently being executed.

### `error`

A boolean indicating if an error occurred during the Axios request.

## Example: Data Fetching

```javascript
import React, { useEffect } from "react";
import { useAxios } from "hookverse";

const DataFetchingExample = () => {
  const { runAxios, data, loading, error } = useAxios({
    url: "https://api.example.com/data",
    method: "GET",
    headers: {
      "Content-Type": "application/json",
    },
  });

  useEffect(() => {
    runAxios();
  }, [runAxios]);

  return (
    <div>
      {loading && <p>Loading...</p>}
      {error && <p>Error occurred while fetching data.</p>}
      {data && (
        <div>
          <p>Data fetched successfully!</p>
          {/* Display data */}
        </div>
      )}
      <button onClick={runAxios} disabled={loading}>
        {loading ? "Loading..." : "Fetch Data"}
      </button>
    </div>
  );
};

export default DataFetchingExample;
```

## Example: Form Submission

```javascript
import React, { useState } from "react";
import { useAxios } from "hookverse";

const FormSubmitExample = () => {
  const [formData, setFormData] = useState({});
  const { runAxios, isExecuting, error } = useAxios({
    url: "https://api.example.com/submit",
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: formData,
  });

  const handleSubmit = () => {
    runAxios();
  };

  const handleInputChange = (e) => {
    const { name, value } = e.target;
    setFormData({ ...formData, [name]: value });
  };

  return (
    <div>
      <form onSubmit={handleSubmit}>
        <input
          type="text"
          name="input1"
          placeholder="Input 1"
          onChange={handleInputChange}
        />
        <input
          type="text"
          name="input2"
          placeholder="Input 2"
          onChange={handleInputChange}
        />
        <button type="submit" disabled={isExecuting}>
          {isExecuting ? "Submitting..." : "Submit Form"}
        </button>
      </form>
      {error && <p>Error occurred while submitting the form.</p>}
    </div>
  );
};

export default FormSubmitExample;
```

In the first example, the `useAxios` hook is utilized to perform an HTTP GET request for data fetching. The `runAxios` function is called to initiate the request, and loading and error states are managed accordingly. Additionally, a button is provided to manually trigger the request, with disabled state based on `loading`.

In the second example, the `useAxios` hook is utilized to perform an HTTP POST request for form submission. The `runAxios` function is called to initiate the request when the form is submitted, and loading and error states are managed accordingly. The submit button is disabled based on `isExecuting` to prevent multiple submissions while the request is in progress. Additionally, any errors that occur during form submission are displayed to the user.

```

```
