# React Components
React components are independent, reusable building blocks in a React application that define what gets displayed on the UI. They accept inputs called props and return React elements describing the UI.

- Components can be reused across different parts of the application to maintain consistency and reduce code duplication.
- Components manage how their output is rendered in the DOM based on their state and props.
- React loads only the necessary components, ensuring optimized performance.
- Only the specific Component updates instead of the whole page.

There are two primary types of React components:
1. Function Components
   - Functional components are simpler and preferred for most use cases.
   - They are JavaScript functions that return React elements.
   - With the introduction of React Hooks, functional components can also manage state and lifecycle events.
       - **Stateless or Stateful:** Can manage state using React Hooks.
       - **Simpler Syntax:** Ideal for small and reusable components.
       - **Performance:** Generally faster since they don’t require a ‘this’ keyword.

```
function Greet(props) {
    return <h1>Hello, {props.name}!</h1>;
}
```

2. Class Components
   - Class components are mainly used when lifecycle methods or error boundaries are required.
   - They include additional features like state management and lifecycle methods.
       - **State Management:** State is managed using the this.state property.
       - **Lifecycle Methods:** Includes methods like componentDidMount, componentDidUpdate, etc.
  
    
        ```
        class Greet extends React.Component {
            render() {
                return <h1>Hello, {this.props.name}!</h1>;
          }
        }
        ```
<hr/>

### Best Practices for React Components
- **Keep Components Small:** *Each component should do one thing well.*
- **Use Functional Components:** *Unless lifecycle methods or error boundaries are required.*
- **Prop Validation:** *Use PropTypes to enforce correct prop types.*
- **State Management:** *Lift state to the nearest common ancestor when multiple components need access.*

### Props in React Components
Props (short for properties) are read-only inputs passed from a parent component to a child component. They enable dynamic data flow and reusability.

- Props are immutable.
- They enable communication between components.

```
function Greet(props) {
    return <h2>Welcome, {props.username}!</h2>;
}

// Usage
<Greet username="Anil" />;
```

### State in React Components
The state is a JavaScript object managed within a component, allowing it to maintain and update its own data over time. Unlike props, state is mutable and controlled entirely by the component.

- State updates trigger re-renders.
- Functional components use the useState hook to manage state.

```
function Counter() {
    const [count, setCount] = React.useState(0);

    return (
        <div>
            <p>Count: {count}</p>
            <button onClick={() => 
                setCount(count + 1)}>Increment</button>
        </div>
    );
}

```

**Note:** Data is passed from parent to child using props. For sibling communication, a shared state or context can be used.

### Rendering a Component
Rendering a component refers to displaying it on the browser. React components can be rendered using the ReactDOM.render() method or by embedding them inside other components.

Ensure the component is imported before rendering.
The ReactDOM.render method is generally used in the root file.

```
ReactDOM.render(<Greeting name="Pooja" />, document.getElementById('root'));
```

### Components in Components
In React, you can nest components inside other components to build a modular and hierarchical structure.

Components can be reused multiple times within the same or different components.
Props can be passed to nested components for dynamic content.

```
function Header() {
    return <h1>Welcome to My Site</h1>;
}

function Footer() {
    return <p>© 2024 My Company</p>;
}

function App() {
    return (
        <div>
            <Header />
            <p>This is the main content.</p>
            <Footer />
        </div>
    );
}

export default App;
```
