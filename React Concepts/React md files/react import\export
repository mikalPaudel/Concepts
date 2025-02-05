# React import/export
In React, importing and exporting components allows you to share and reuse code across different files. Components can be exported using either default or named exports, and then imported into other files to be used.

1. Default Export and Import
   - A file can have only one default export.
   - When importing, you can name it anything.


   ```jsx
   // Export (MyComponent.js)
   export default function MyComponent() {
       return <h1>Hello</h1>;
   }
   
   // Import (App.js)
   import Hello from './MyComponent'; // Can be named anything and used like <Hello/>

   ```
    
2. Named Export and Import
   - A file can have multiple named exports.
   - When importing, you must use curly braces and the exact name.
  
   ```jsx
   // Export (utils.js)
   export function add(a, b) { return a + b; }
   export function subtract(a, b) { return a - b; }
   
   // Import (App.js)
   import { add, subtract } from './utils';

   ```
     
3. Combining Default and Named Exports
   - You can export both default and named components from the same file.
  
   ```jsx
   // Export (MyModule.js)
   export default function MainComponent() { return <h1>Main</h1>; }
   export function HelperComponent() { return <h2>Helper</h2>; }
   
   // Import (App.js)
   import MainComponent, { HelperComponent } from './MyModule';

   ```

4. Exporting Multiple Components from the Same File
   - Instead of exporting components from separate files, you can group them.

   ```jsx
   // Export (Components.js)
   export function Header() { return <header>Header</header>; }
   export function Footer() { return <footer>Footer</footer>; }
   
   // Import (App.js)
   import { Header, Footer } from './Components';

   ```

### When to Use Default Export
- Use for a single primary functionality or component in a file.
- When you want flexibility in naming during import.
- Ideal for components or modules that represent the main purpose of the file.
  
### When to Use Named Export
- Use when exporting multiple functionalities or components from the same file.
- When you want consistency in import names.
- Useful for utility functions, constants, or multiple related components.
