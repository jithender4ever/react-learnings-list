# react-learnings-list

List of key learnings and/or tips/best practices

## Conditional Rendering

- When you like to render some content conditionally, make sure you check for a `Boolean` value and not for a `falsy` value.
  **Eg:**

  ```jsx
  const myList = [];

  <div>{myList.length && "Your Name"}</div> // 0

  // To fix this,

  <div>{myList.length > 0 && "Your Name"}</div> // "Your Name"
  ```

  - If you need to display a boolean value, then convert it to a String.

## Use of children prop

- `children` is a special prop which is always made available to a Component and can be accessed as `props.children`.

  **Eg:**

  ```jsx
  function Home() {
    return (
      <div>
        <Main>
          <LeftNav />
          <RightNav />
        </Main>
      </div>
    );
  }

  function Main({ children }) {
    return <div>{children}</div>;
  }
  ```

## Styling methodologies

- At a high level there are 2 types of methodologies that are most commonly used - `CSS-in-CSS` and `CSS-in-JS`.

  **CSS-in-CSS:**

  - Having a `.css` file alongside the react component and importing it for usage is most basic, but the biggest drawback is that all styles are `global`. So, this is not a recommended approach.
  - `CSS Modules` solves this problem and all the css files should be named as `***.module.css`. These can co-exist with the react components and can be imported and used without any conflicts.
    **Note:** 1. CSS Modules will work out of the box for applications that are created using `CRA`. But for others, `webpack` configuration is needed.

  **CSS-in-JS:**

  - `Styled Components` is an example of this implementation.
  - `Material-UI` also follows this approach.
    - `Material-UI` also implements this using HOC flavor.
