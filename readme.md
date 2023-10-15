# Readme.md

## Logical Operators

- **`&&` Operator**: It seeks out the first falsy value.
- **`||` Operator**: It's on the lookout for the first truthy value.

## JSON.stringify()

The `JSON.stringify()` method is your go-to tool for turning a JavaScript value into a JSON string.

- **Usage**: `JSON.stringify(value)`
- **Usage with Options**: `JSON.stringify(value, replacer, space)` (optional parameters)

## JSON.parse()

The `JSON.parse()` method steps in when you need to dissect a JSON string and transform it into a JavaScript object or value.

## Window: localStorage Property

The `localStorage` property, tucked within the window interface, provides an entry point to a `Storage` object that belongs to the document's origin. The data stashed in `localStorage` stays put across different browser sessions.

- **Comparison with `sessionStorage`**: Unlike `localStorage`, data held in `sessionStorage` makes its exit when the page session concludes—typically when you close the page. Bear in mind that `localStorage` data linked to a document loaded in a "private browsing" or "incognito" session clears out when the last "private" tab says goodbye.

- **Handling Empty Keys**: If the key comes up empty, `localStorage` hands you a `null`.

- **Usage**:
  - `localStorage.setItem("key", "value")` // Just a note: The value should be in the form of strings.
  - `localStorage.getItem("key")`

## `useState` Lazy Initialization

When you're grappling with weighty computations or IO operations, and you've got your heart set on running them during the initial render but not when the page decides to freshen up, the `useState` hook can lend a hand. 

```javascript
const value = SomethingHeavyComputationally(); // It could be any IO operation.

// Here's the catch: every re-render gives that heavy function another workout. To avoid this, consider the art of lazy initialization.

const [state, setState] = useState(value);

// Or take it up a notch by crafting a function that only takes a bow during the initial performance—no encore during the re-runs. This is what they call lazy initial state loading.
// const value = () => SomethingHeavyComputationally();

// flash cards link https://www.revisely.com/flashcards/packs/5WaQD
to revise till now 
# react-notes-flashcards
