# React Components
React components are independent, reusable building blocks in a React application that define what gets displayed on the UI. They accept inputs called props and return React elements describing the UI.

- Components can be reused across different parts of the application to maintain consistency and reduce code duplication.
- Components manage how their output is rendered in the DOM based on their state and props.
- React loads only the necessary components, ensuring optimized performance.
- Only the specific Component updates instead of the whole page.

There are two primary types of React components:
1. Function Components
2. Class Components

### Best Practices for React Components
- **Keep Components Small:** *Each component should do one thing well.*
- **Use Functional Components:** *Unless lifecycle methods or error boundaries are required.*
- **Prop Validation:** *Use PropTypes to enforce correct prop types.*
- **State Management:** *Lift state to the nearest common ancestor when multiple components need access.*

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
