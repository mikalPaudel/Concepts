# React Conditional Rendering
Conditional rendering in React refers to rendering certain components or UI elements based on specific conditions. 
You can think of it as a way to display different content depending on the state of your application 
or the value of variables.

## Ways to Implement Conditional Rendering in React
### 1. Using If/Else Statements
You can use JavaScript’s if and else statements to render components conditionally.
This method works well when the condition is more complex.

```
import React, { useState } from 'react';

function App() {
    const [isLogged, setIsLogged] = useState(false);

    if (isLogged) {
        return <h1>Welcome back, User!</h1>;
    } else {
        return <button onClick={() => 
            setIsLogged(true)}>Login</button>;
    }
}

export default App;
```

In this example, the component will render either a “Welcome back” message 
or a login button depending on the isLogged state.

### 2. Using Ternary Operator
The ternary operator (condition ? expr1 : expr2) is a concise way to conditionally render JSX elements.
It’s often used when the logic is simple and there are only two options to render.

```
import React, { useState } from 'react';

function App() {
    const [isLogged, setIsLogged] = useState(false);

    return (
        <div>
            {isLogged ? (
                <h1>Welcome back, User!</h1>
            ) : (
                <button onClick={() => setIsLogged(true)}>Login</button>
            )}
        </div>
    );
}

export default App;
```

Here, if isLogged is true, it shows a “Welcome back” message, otherwise, it displays a login button.

### 3. Using Logical AND (&&) Operator
In JavaScript, the && operator returns the second operand if the first is true, and nothing if the first is false. This can be useful when you only want to render something when a condition is true.

```
import React, { useState } from 'react';

function App() {
    const [isLogged, setIsLogged] = useState(false);

    return (
        <div>
            <button onClick={() => setIsLogged(!isLogged)}>
                Toggle Login
            </button>
            {isLogged && <h1>Welcome back, User!</h1>}
        </div>
    );
}

export default App;
```

In this case, the “Welcome back” message only appears if isLogged is true. If false, it renders nothing.

### 4. Using Switch Case Statements
Switch case statements are useful when you need to handle multiple conditions, which would otherwise require multiple if conditions. This approach can be more readable if there are many conditions to check.

```
import React, { useState } from 'react';

function App() {
    const [status, setStatus] = useState('guest');

    const render = () => {
        switch (status) {
            case 'guest':
                return <button onClick={() => 
                    setStatus('user')}>Login</button>;
            case 'user':
                return <h1>Welcome, User!</h1>;
            case 'admin':
                return <h1>Admin Dashboard</h1>;
            default:
                return null;
        }
    };

    return <div>{render()}</div>;
}

export default App;
```

Here, based on the status value, different content is rendered for guest, user, or admin.

## Practical Use Cases for Conditional Rendering
### 1. Displaying User Profile Based on Authentication
You can conditionally render a user’s profile page if the user is logged in, or a login form if not.

```
import React, { useState } from 'react';

function App() {
    const [isAuthenticated, setIsAuthenticated] = useState(false);

    return (
        <div>
            {isAuthenticated ? (
                <h1>User Profile</h1>
            ) : (
                <button onClick={() => 
                    setIsAuthenticated(true)}>Log In</button>
            )}
        </div>
    );
}

export default App;
```

### 2. Showing Loading State
You can display a loading spinner or message while waiting for data to be fetched.

```
import React, { useState, useEffect } from 'react';

function App() {
    const [isLoading, setIsLoading] = useState(true);
    const [data, setData] = useState(null);

    useEffect(() => {
        setTimeout(() => {
            setData('Fetched Data');
            setIsLoading(false);
        }, 2000);
    }, []);

    return (
        <div>
            {isLoading ? (
                <h1>Loading...</h1>
            ) : (
                <h1>{data}</h1>
            )}
        </div>
    );
}

export default App;
```

Here, the “Loading…” message will be displayed until the data is fetched, after which the fetched data will be shown.

### Best Practices for Conditional Rendering
- **Keep it simple:** Try to avoid deeply nested conditions, as it can make the component hard to read and maintain. Use ternary operators or helper functions where possible.
- **Early returns:** Consider using early returns to handle conditions upfront, especially when there’s more than one condition.
- **Component-based rendering:** If the conditional rendering logic is complex, consider breaking it into smaller components to improve readability and reusability.
