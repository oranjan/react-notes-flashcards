Here's the provided content formatted in Markdown:

```markdown
# React Notes and Flashcards

## Flash Cards
- [Access Flash Cards 1](https://www.revisely.com/flashcards/packs/5WaQD)
- [Access Flash Cards 2](https://www.revisely.com/flashcards/packs/tL9TC)

## Logical Operators

Understanding logical operators is fundamental in React development:

- **`&&` Operator**: It evaluates expressions and seeks the first falsy value.
- **`||` Operator**: It evaluates expressions and looks for the first truthy value.

## JSON.stringify()

The `JSON.stringify()` method is a powerful tool for converting JavaScript values into JSON strings.

- **Usage**: `JSON.stringify(value)`
- **Usage with Options**: `JSON.stringify(value, replacer, space)` (optional parameters)

## JSON.parse()

When you need to parse a JSON string and transform it into a JavaScript object, rely on the `JSON.parse()` method.

## Window: localStorage Property

Understanding the `localStorage` property and its differences from `sessionStorage` is crucial:

- **Comparison with `sessionStorage`**: Unlike `localStorage`, data stored in `sessionStorage` vanishes when the page session ends, typically upon closing the page. Be aware that `localStorage` data associated with a document loaded in a "private browsing" or "incognito" session is wiped when the last "private" tab is closed.

- **Handling Empty Keys**: If a key is empty, `localStorage` returns `null`.

- **Usage**:
  - `localStorage.setItem("key", "value")` (Note: The value should be in string format)
  - `localStorage.getItem("key")`

## `useState` Lazy Initialization

Optimize the performance of your React components by using `useState` lazy initialization when dealing with heavy computations or IO operations.

```javascript
const value = SomethingHeavyComputationally(); // It could be any IO operation.

// To avoid re-running heavy computations, use lazy initialization:
const [state, setState] = useState(value);

// Alternatively, create a function that only runs during the initial render, achieving lazy initial state loading.
// const value = () => SomethingHeavyComputationally();
```

## React Event Handlers

In React components, event handlers automatically receive an event object as a parameter when invoked. Here's an example:

```javascript
const text = "A brown fox jumped over...";

const subtext = text.split("x");

console.log(subtext); // ["A brown fo",""]
```

## File Paths

Understanding absolute and relative file paths is essential:

- Absolute Path: `/path/to/your/file`
- Relative Path: `./relative/path/to/your/file`

## NavLink Styling

You can style NavLink components using a function or class based on the current route:

Example: Styling the "About" link in the navbar. If you're on the "About" page, the link is red; otherwise, it's the normal color.

```javascript
const styles = {
  fontWeight: 'bold',
  textDecoration: 'underline',
  color: "#161616"
};

<NavLink
  style={({ isActive }) => isActive ? styles : {}}
  About
</NavLink>

// You can also use a class:
className={({ isActive }) => isActive ? "my-link" : null }
```

## Understanding `.parse` and `.json()`

Differentiating between `.parse()` and `.json()` in JavaScript:

1. `.parse`:
   - Use `.parse()` to convert a JSON-formatted string into a JavaScript object.

2. `.json()`:
   - Employ `.json()` in HTTP requests to extract and parse JSON response data.

## React `useEffect`

A practical example of using `useEffect` to fetch data from an API:

```javascript
React.useEffect(() => {
  const fetchData = async () => {
    try {
      const response = await fetch(apiUrl);
      const jsonData = await response.json();
      console.log(jsonData);
    } catch (error) {
      console.error('Error fetching data:', error);
    }
  };

  fetchData();
}, []);
```

Replace `apiUrl` with your actual API endpoint.

## Daily Update 17 Oct '23
- Today, I've studied for 5.5 hours, and it feels great. I'm wearing an extra layer because it's cold outside, but the nice weather makes it worth it. Hopefully, the extra layer will keep me from getting sick.
```

# HTTP Methods and API Basics

## HTTP Methods
- HTTP stands for Hypertext Transfer Protocol.
- A protocol is an agreed-upon, standard way of doing something.
- The protocol in a URL is represented by the part before "://," e.g., "https."
- When requesting data from an API, the most common method used is GET.

## API (Application Programming Interface)
- An API is any tool that helps your program connect and communicate with another program.
- We use APIs to get data from servers.
- APIs can be pre-written code that performs various tasks, such as the DOM API, Array method API, and local storage.
- 3rd party APIs are provided by external services.
- A server is a computer that listens to requests from devices (e.g., PC, mobile) and returns responses.
- The client is the entity that sends requests to the server.

## Request and Response
- A request is made by a client to ask for something, like resources, HTML, fonts, videos, images, or JSON.
- The server listens to requests and responds, either fulfilling the request or not.

## JSON (JavaScript Object Notation)
- JSON stands for JavaScript Object Notation.
- JSON objects have keys enclosed in double quotes and don't have a trailing comma.
- It is a stringified JavaScript object and cannot contain functions.
- XMLHttpRequest (XHR) requests are often used to get JSON responses.

## Asynchronous JavaScript
- Asynchronous JavaScript allows out-of-order execution of code.
- You can use `fetch` to make asynchronous requests to APIs.

## HTTP Basics
1. What does HTTP stand for? Hypertext Transfer Protocol.
2. How would you describe what a protocol is to a complete newbie? An agreed-upon, standard way of doing something.
3. Which part of this URL describes the protocol? The part before "://," e.g., "https."
4. What request method do you use when asking for data from an API? GET.

## Base URL and Endpoint
- A Base URL is the part of the URL that doesn't change, e.g., "https://blahblahblah.com/api/v2."
- An Endpoint specifies exactly which resource you want to get from the API.

Given the following URLs from an example API:
- Base URL: https://blahblahblah.com/api/v2
- Available endpoints: /users, /products, /products/<some-id-of-a-product-here>

## Real-World Usage of HTTP Methods
- GET: Retrieving weather information, accessing the database.
- POST: Creating a new screencast, adding data to the database.
- PUT: Marking items as "completed" on a shared todo list, updating data in the database.
- DELETE: Deleting unnecessary messages on Slack, removing data from the database.

## Request Body and Headers
- A request body is used to send data to the server, primarily with POST and PUT requests. The data must be converted into JSON.
- Headers provide additional information about the request.

## REST (Representational State Transfer)
- REST is a design pattern for standard communication between clients and servers.
- REST principles:
  1. Client and server separation.
  2. Statelessness: Servers do not remember previous requests.

## Nouns and Verbs in REST
- In REST, API endpoints are typically represented by nouns (e.g., /bikes) and HTTP methods are the verbs.
- Query strings and URL parameters are used to specify data in requests.

For more details on REST API, refer to [this presentation](https://docs.google.com/presentation/d/e/2PACX-1vTEztADtG8OhJ4695LYwtVftNgriQK7zAOsYNru9OfaPA1mQEAlkNd1BqgOdec1aZRC6PxSxOnlrBeH/pub?start=false&loop=false&delayms=3000&slide=id.gd92b27aadb_0_310).

Remember that HTTP is single-threaded, which means commands are executed one at a time.

# useContext

To avoid prop drilling, we use `useContext` in React:

```javascript
import { createContext } from "react";

const ThemeContext = createContext();

// Wrap your app with the Provider:
ReactDOM.render(
  <ThemeContext.Provider value="light">
    <App />
  </ThemeContext.Provider>,
  document.getElementById("root")
);

// Consume the context in your child component:
const value = useContext(ThemeContext);

console.log(value); //light
```

This allows you to share values between components without passing props through all levels of the component tree.

## Daily Update 17 Oct '23

- Today, I've studied for 5.5 hours, and it feels great. I'm wearing an extra layer because it's cold outside, but the nice weather makes it worth it. Hopefully, the extra layer will keep me from getting sick.

# HTTP Methods and API Basics

## HTTP Methods
- HTTP stands for Hypertext Transfer Protocol.
- A protocol is an agreed-upon, standard way of doing something.
- The protocol in a URL is represented by the part before "://," e.g., "https."
- When requesting data from an API, the most common method used is GET.

## API (Application Programming Interface)
- An API is any tool that helps your program connect and communicate with another program.
- We use APIs to get data from servers.
- APIs can be pre-written code that performs various tasks, such as the DOM API, Array method API, and local storage.
- 3rd party APIs are provided by external services.
- A server is a computer that listens to requests from devices (e.g., PC, mobile) and returns responses.
- The client is the entity that sends requests to the server.

## Request and Response
- A request is made by a client to ask for something, like resources, HTML, fonts, videos, images, or JSON.
- The server listens to requests and responds, either fulfilling the request or not.

## JSON (JavaScript Object Notation)
- JSON stands for JavaScript Object Notation.
- JSON objects have keys enclosed in double quotes and don't have a trailing comma.
- It is a stringified JavaScript object and cannot contain functions.
- XMLHttpRequest (XHR) requests are often used to get JSON responses.

## Asynchronous JavaScript
- Asynchronous JavaScript allows out-of-order execution of code.
- You can use `fetch` to make asynchronous requests to APIs.

## HTTP Basics
1. What does HTTP stand for? Hypertext Transfer Protocol.
2. How would you describe what a protocol is to a complete newbie? An agreed-upon, standard way of doing something.
3. Which part of this URL describes the protocol? The part before "://," e.g., "https."
4. What request method do you use when asking for data from an API? GET.

## Base URL and Endpoint
- A Base URL is the part of the URL that doesn't change, e.g., "https://blahblahblah.com/api/v2."
- An Endpoint specifies exactly which resource you want to get from the API.

Given the following URLs from an example API:
- Base URL: https://blahblahblah.com/api/v2
- Available endpoints: /users, /products, /products/<some-id-of-a-product-here>

## Real-World Usage of HTTP Methods
- GET: Retrieving weather information, accessing the database.
- POST: Creating a new screencast, adding data to the database.
- PUT: Marking items as "completed" on a shared todo list, updating data in the database.
- DELETE: Deleting unnecessary messages on Slack, removing data from the database.

## Request Body and Headers
- A request body is used to send data to the server, primarily with POST and PUT requests. The data must be converted into JSON.
- Headers provide additional information about the request.

## REST (Representational State Transfer)
- REST is a design pattern for standard communication between clients and servers.
- REST principles:
  1. Client and server separation.
  2. Statelessness: Servers do not remember previous requests.

## Nouns and Verbs in REST
- In REST, API endpoints are typically represented by nouns (e.g., /bikes) and HTTP methods are the verbs.
- Query strings and URL parameters are used to specify data in requests.

For more details on REST API, refer to [this presentation](https://docs.google.com/presentation/d/e/2PACX-1vTEztADtG8OhJ4695LYwtVftNgriQK7zAOsYNru9OfaPA1mQEAlkNd1BqgOdec1aZRC6PxSxOnlrBeH/pub?start=false&loop=false&delayms=3000&slide=id.gd92b27aadb_0_310).

Remember that HTTP is single-threaded, which means commands are executed one at a time.

# useContext

To avoid prop drilling, we use `useContext` in React:

```javascript
import { createContext } from "react";

const ThemeContext = createContext();

// Wrap your app with the Provider:
ReactDOM.render(
  <ThemeContext.Provider value="light">
    <App />
  </ThemeContext.Provider>,
  document.getElementById("root")
);

// Consume the context in your child component:
const value = useContext(ThemeContext);

console.log(value); //light





```  
## Rejected Promises and Error Handling

If a promise is rejected (an error occurs), you can handle it using the `.catch` method or by using `Promise.reject()`.

Here's an example of using `async` and `await` to fetch data from an API:

```javascript
async function fetchData() {
  try {
    const response = await fetch(API);
    if (!response.ok) {
      throw new Error('Failed to fetch data');
    }
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}
```

In this example, `async` and `await` are used to make the asynchronous code more readable, and error handling is done using `try...catch`. If the API request fails, it will be caught and handled in the `catch` block.
```

```
## HTTP Status Codes:

- Status code 200 indicates a successful request with the requested data.
- Status code 404 indicates that the requested resource was not found.
- HTTP status codes can be categorized into 1xx (Informational), 2xx (Successful), 3xx (Redirection), 4xx (Client Error), and 5xx (Server Error).

## Using `res.ok` in JavaScript:

- `res.ok` is a Boolean property indicating if the HTTP response was successful (status code in the 200-299 range).
- If `res.ok` is `true`, the response was successful; if `false`, there was an error.
- It's commonly used for error checking in Fetch API.

## `.catch()` Block in Promise Chains:

- Used for error handling in promise chains.
- Placed at the end of the chain to catch and handle any errors thrown in previous `then` blocks.
- It's crucial for handling errors in asynchronous operations.
- You can handle errors in various ways, such as logging, displaying messages, or retrying operations.

## Handling HTTP Errors with Fetch:

- Fetch API only rejects promises on network errors, not on HTTP errors.
- To handle HTTP errors, check the `ok` property of the `Response` object.
- If `ok` is `false`, the response was not successful (e.g., 404 or 500 error).
- Create a function to handle HTTP errors and use it in your code.

Example:

```javascript
async function fetchWithErrorHandler(url) {
  const response = await fetch(url);

  if (!response.ok) {
    // Handle the HTTP error here.
  }

  return response;
}
```

Handle HTTP errors using try-catch:

```javascript
try {
  const response = await fetchWithErrorHandler('https://example.com/api/users');
  const data = await response.json();
  // Handle the data.
} catch (error) {
  // Handle HTTP errors here.
}
```

In summary, use `res.ok` for network response status, and handle HTTP errors using custom functions and try-catch blocks for a better understanding of the success or failure of a network request.

To remove the seconds part from the above code, we can use the following JavaScript code:

```javascript
const date = new Date();
const time = date.toLocaleTimeString('hi-IN', {
  hour: 'numeric',
  minute: 'numeric',
});
```

This code will return the time in Hindi, including the hour and minute, but without the seconds.

Output:
```
रात 8:00 बजे
```

We can also use the `toLocaleDateString()` method to return the date in Indian locale without the seconds.
```

The text is now formatted in Markdown, making it more readable and structured.