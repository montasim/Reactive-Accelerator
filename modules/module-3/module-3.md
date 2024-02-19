## [Module 3 - React State Management Deep Dive](module-3.md)

<br/>

### Table of Contents

- [Lesson](#lesson)

<br/>

### Lesson

[3.1 Declarative vs Imperative UI](./modules/module-3/#3-1-declarative-vs-imperative-ui)

[3.2 Thinking about UI declaratively in React - Finding Visual States](./modules/module-3/#3-2-thinking-about-ui-declaratively-in-react-finding-visual-states)

[3.3 Thinking about UI declaratively in React - Finalize React states & Connect Event Handlers](./modules/module-2/#3-3-thinking-about-ui-declaratively-in-react-finalize-react-states-connect-event-handlers)

[3.4 Choosing the State Structure - Group related state](./modules/module-3/#3-4-choosing-the-state-structure-group-related-state)

[3.5 Choosing the State Structure - Avoid contradictions in state](./modules/module-3/#3-5-choosing-the-state-structure-avoid-contradictions-in-state)

[3.6 Choosing the State Structure - Avoid redundant state](./modules/module-3/#3-6-choosing-the-state-structure-avoid-redundant-state)

[3.7 Choosing the State Structure - Avoid duplication in state](./modules/module-3/#3-7-choosing-the-state-structure-avoid-duplication-in-state)

[3.8 Choosing the State Structure - Avoid deeply nested state](./modules/module-3/#3-8-choosing-the-state-structure-avoid-deeply-nested-state)

[3.9 Sharing State Between Components - Lifting state up](./modules/module-3/#3-9-sharing-state-between-components-lifting-state-up)

[3.10 Preserving and Resetting State - Default behavior](./modules/module-3/#3-10-preserving-and-resetting-state-default-behavior)

[3.11 Resetting state at the same position - Changing Default behavior](./modules/module-3/#3-11-resetting-state-at-the-same-position-changing-default-behavior)

[3.12 Extracting State Logic into a Reducer - Example project](./modules/module-3/#3-12-extracting-state-logic-into-a-reducer-example-project)

[3.13 Three steps to Consolidate state logic with a reducer](./modules/module-3/#3-13-three-steps-to-consolidate-state-logic-with-a-reducer)

[3.14 Comparing useState and useReducer - How to write reducers well](./modules/module-3/#3-14-comparing-usestate-and-usereducer-how-to-write-reducers-well)

[3.15 Writing concise reducers with Immer](./modules/module-3/#3-15-writing-concise-reducers-with-immer)

[3.16 Passing Data Deeply with Context - Introduction to Context API](./modules/module-3/#3-16-passing-data-deeply-with-context-introduction-to-context-api)

[3.18 Context passes through intermediate components](./modules/module-3/#3-18-context-passes-through-intermediate-components)

[3.19 Some notes and use cases for Context](./modules/module-3/#3-19-some-notes-and-use-cases-for-context)

[3.20 Scaling Up with Reducer and Context](./modules/module-3/#3-20-scaling-up-with-reducer-and-context)

[3.21 Project Tutorial - CineRental: Your One-Stop React App for Movie Magic and Rentals](./modules/module-3/#3-21-project-tutorial-cinerental-your-one-stop-react-app-for-movie-magic-and-rentals)

[Assignment 3 Requirements - Improved Tasker](./modules/module-3/#assignment-3-requirements-improved-tasker)

<br/>
<br/>

### 3.1 Declarative vs Imperative UI

<br/>

**1. What is Declarative approach?**

   **Answer:** A declarative approach in programming refers to expressing the logic of a program without explicitly specifying the control flow. Instead of providing step-by-step instructions on how to achieve a task, developers declare what they want to accomplish, and the underlying system figures out how to achieve it.
   
   In a declarative approach:
   
   1. **Focus on What, Not How**: Developers focus on describing the desired outcome or result rather than the specific steps to achieve it.
   
   2. **Abstraction of Control Flow**: The control flow is abstracted away from the main logic, allowing the underlying system or framework to handle it.
   
   3. **Higher Level of Abstraction**: Code tends to be more abstract and expressive, often leveraging higher-level constructs or domain-specific languages.
   
   4. **Less Boilerplate Code**: Declarative programming often leads to cleaner and more concise code, as developers don't need to write repetitive or low-level control flow logic.
   
   5. **Easier to Understand and Maintain**: Declarative code tends to be more readable and easier to maintain, as it focuses on the intent of the program rather than implementation details.

   Examples of declarative approaches in programming include:
   
   - **Functional Programming**: Functional programming languages like Haskell, Clojure, or functional features in languages like JavaScript promote a declarative style by emphasizing pure functions and immutable data.
   
   - **Declarative UI Frameworks**: Libraries and frameworks like ReactJS, Vue.js, or SwiftUI for iOS development allow developers to describe the user interface in terms of state and components, abstracting away the imperative DOM manipulation or UI updates.
   
   - **SQL**: SQL (Structured Query Language) is a declarative language used for querying and manipulating databases. Instead of specifying how to retrieve data from a database, developers declare the data they want to retrieve using SQL queries.
   
   Overall, the declarative approach simplifies development by allowing developers to express their intentions clearly while leaving the details of implementation to the underlying system or framework. This often results in more maintainable, scalable, and less error-prone code.

<br/>

**2. What is Imperative approach?**

   **Answer:** An imperative approach in programming refers to a style where developers write code that explicitly dictates the steps the computer must take to achieve a goal. This contrasts with the declarative approach, where developers focus on the "what" rather than the "how."

   In an imperative approach:

   1. **Focus on How, Not What**: Developers provide detailed, step-by-step instructions on how tasks should be performed to achieve a specific outcome.

   2. **Explicit Control Flow**: The control flow of the program is directly managed by the programmer, using loops, conditional statements, and other control structures.

   3. **Lower Level of Abstraction**: Code tends to be more verbose, with a greater focus on algorithmic details and less on abstracting away the implementation.

   4. **More Boilerplate Code**: Imperative programming often requires more boilerplate code, as developers must explicitly state all operations and state changes.

   5. **Greater Control and Precision**: It offers developers more control over program execution and state management, which can be advantageous for certain low-level tasks or performance-critical applications.

   Examples of imperative approaches in programming include:

   - **Procedural Programming**: Languages like C and Pascal support procedural programming, a subtype of imperative programming focusing on procedures or routines to perform tasks.

   - **Object-Oriented Programming (OOP)**: While OOP can support higher-level abstractions, languages like Java and C++ also allow for imperative programming by defining methods that describe step-by-step operations on objects' states.

   - **Scripting and Automation**: Scripting languages such as Python and Bash are often used in an imperative style for automation tasks, where explicit control over the execution flow is necessary.

   Overall, the imperative approach provides a direct and explicit way to manipulate a program's state, offering precise control over its behavior. While it may lead to more verbose and complex code compared to declarative styles, it remains foundational to understanding computational logic and is indispensable for many areas of software development and system programming.

<br/>

**3. Why React is Considered a Declarative Approach?**

   **Answer:** React, a popular JavaScript library for building user interfaces, is often described as declarative because of how it allows developers to create UIs. Unlike imperative programming, which requires explicit instructions on how to achieve a result, React focuses on defining the desired end state of the UI and lets the library figure out the operations needed to achieve that state.

   Key Aspects of React's Declarative Nature
   
   1. **Component-Based Architecture**: React encourages the use of components to describe the UI structure. Developers declare components as reusable pieces, specifying what should be rendered without detailing the manipulation of the DOM directly.
   
   2. **State and Props**: React components are defined by their state and properties (props). When the state or props of a component change, React automatically updates the component in the DOM. This means developers simply declare the state of the UI at any point in time, and React takes care of the rendering logic.
   
   3. **Virtual DOM**: React uses a virtual DOM to improve performance and simplify the programming model. Developers work with a high-level abstraction—the virtual DOM—by declaring their UI's desired state. React then efficiently updates the actual DOM to match this state, abstracting away direct DOM manipulation and the imperative steps needed to update the UI.
   
   4. **JSX**: JSX is a syntax extension for JavaScript that resembles HTML. It allows developers to write their components and UI descriptions in a way that looks similar to HTML but actually creates React elements. This syntax further supports the declarative approach by letting developers describe what the UI should look like in a syntax that is both familiar and expressive.
   
   5. **Unidirectional Data Flow**: React enforces a unidirectional data flow, which makes the state management more predictable. The flow of data from parent to child components (via props) encourages a cleaner, more modular approach to building UIs, where the state is often managed in higher-level components. This structure makes it easier to understand and predict UI changes, aligning with the declarative paradigm of specifying "what" should happen rather than "how."
   
   Benefits of React's Declarative Approach
   
   - **Simplicity**: Writing declarative code in React makes it easier to reason about how the UI should look and behave at any given point in time.
   - **Maintainability**: Since the declarative code focuses on the what rather than the how, it tends to be more readable and maintainable.
   - **Efficiency**: React's reconciliation algorithm optimizes rendering by updating only parts of the UI that have changed, a process abstracted away from the developer.
   
   In conclusion, React's declarative approach simplifies the process of building and maintaining complex user interfaces by abstracting away the direct manipulation of the DOM and focusing on the desired outcome of the UI.

<br/>

### 3.2 Thinking about UI declaratively in React - Finding Visual States

<br/>

   **1. Solving Problems in React Using a Declarative Approach?**
   
   **Answer:** 
   
   1. Define the Desired State
   
      Start by clearly defining the UI's desired end state for any given set of conditions or inputs. In React, this often involves planning your component's state (`useState`) and props structure, determining what data your component needs to render correctly.
      
      **Example:** If you're building a to-do list, decide what information each to-do item will contain (e.g., title, description, due date, completed status) and how you will track these items in your component's state.
   
   2. Break the UI into Components
   
      React's component-based architecture lets you break down the UI into reusable pieces. Each component should be responsible for a specific piece of the UI, following the single responsibility principle.
      
      **Example:** For a to-do list application, you might have components for the list itself, individual to-do items, a form to add new items, and buttons for filtering items based on their completion status.
   
   3. Use JSX to Declare UI Elements
   
      JSX allows you to describe your UI in a syntax similar to HTML but with the power of JavaScript. Use JSX to declaratively describe what each component should render, based on the component's state and props.
      
      **Example:** Create a `ToDoItem` component that takes a to-do item as a prop and renders the item's title and a checkbox indicating its completion status.
   
   4. Manage State and Props for Dynamic Content
   
      React's state management is key to implementing a declarative approach. Use state and props to manage dynamic content, triggering UI updates automatically when the state changes.
      
      **Example:** Use `useState` to track the list of to-do items. When a new item is added, update the state. React will automatically re-render the components that depend on this state, reflecting the changes in the UI.
   
   5. Leverage Conditional Rendering
   
      Conditional rendering in React allows you to declaratively specify different UI elements to display under different conditions. Use JavaScript logical operators (`&&`, `? :`) or `if-else` statements within your JSX to describe these conditions.
      
      **Example:** Display a message when the to-do list is empty, or the list of items if it's not. You can use the `&&` operator to only render the list if it contains items.
   
   6. Abstract Common Functionality into Custom Hooks
   
      For complex logic or side effects (like fetching data), abstract this functionality into custom hooks. This keeps your component code clean and focuses on describing the UI rather than the logic behind it.
      
      **Example:** Create a `useToDoItems` hook that fetches to-do items from an API and manages the state of these items. This hook can be reused across any component that needs to display or interact with to-do items.
   
   7. Optimize Performance Declaratively
   
      React provides hooks like `useMemo` and `useCallback` to optimize performance declaratively. Use these hooks to memoize expensive calculations or callbacks that depend on specific state or props, preventing unnecessary re-renders.
      
      **Example:** Use `useMemo` to calculate the number of completed to-do items only when the list of items changes, not on every render.

   **Conclusion**

   By focusing on the desired state of your UI and letting React handle the how, you can solve problems more intuitively and efficiently. This declarative approach leads to code that is easier to read, understand, and maintain, ultimately making you a more effective developer.

   <br/>

   **2. What are Living Style Guides or Storybook?**
   
   **Answer:** 
   
   **Living Style Guides** are dynamic documentation systems that showcase a library of the design components (such as buttons, forms, typography, etc.) used in web and mobile app development. Unlike static style guides, which are often presented as PDFs or static web pages, living style guides are interactive, reflecting real-time changes made to the components. They serve as a single source of truth for both designers and developers, ensuring consistency in the user interface across different parts of an application or even across multiple projects.

   **Storybook** is a popular example of a living style guide or component explorer. It is an open-source tool that allows developers to create isolated UI components independently from the main application. With Storybook, components can be developed and tested in isolation from the business logic of the app, which simplifies the development process, enhances component reuse, and improves testing efficiency.
   
   **Key Features of Living Style Guides and Storybook**
   
   1. **Interactive Component Library**: Provides an interactive environment to view and interact with components, including changing props, states, and simulating user interactions.
   
   2. **Isolation**: Components are developed and tested in isolation, making it easier to identify and fix issues without side effects on the rest of the application.
   
   3. **Documentation**: Supports inline documentation for components, including usage guidelines, design notes, and code examples, ensuring that all team members understand how to use and implement the components correctly.
   
   4. **Customization and Extensibility**: Allows for customization and addition of plugins or add-ons to extend functionality, such as accessibility testing, internationalization, and more.
   
   5. **Version Control Integration**: Can be integrated with version control systems to keep the component library up-to-date with the latest design and code changes.
   
   **Benefits of Using Living Style Guides or Storybook**
   
   - **Consistency**: Ensures UI consistency across an application or multiple projects by providing a single reference point for design components.
   
   - **Efficiency**: Accelerates the development process by allowing developers and designers to work on components in isolation and reuse components across different parts of an application.
   
   - **Collaboration**: Facilitates better collaboration between design and development teams by providing a common language and clear documentation of components.
   
   - **Quality**: Improves the quality of the final product by enabling thorough testing of components in various states and scenarios.
   
   **Conclusion**
   
   Living style guides and tools like Storybook represent a significant evolution in the way design systems are created and maintained. By providing a dynamic, interactive library of components, they help teams build more consistent, efficient, and high-quality web and mobile applications.

<br/>

### 3.3 Thinking about UI declaratively in React - Finalize React states & Connect Event Handlers

<br/>

**1. Uncontrolled way of handling forms in React?**

**Answer:** 

**Uncontrolled components** in React are those that store their own state internally and update it based on user input without the involvement of the React component's state. This is the traditional HTML way of handling form inputs.

**How Uncontrolled Components Work:**

In an uncontrolled component, you typically use a `ref` to directly access the DOM element and its value when needed, rather than syncing the input's current value with the component's state. This approach is similar to traditional HTML form handling.

**Implementing Uncontrolled Components:**

To implement an uncontrolled component in React:

1. **Use Refs**: Utilize `React.createRef()` to create a ref and assign it to the input element. This ref provides direct access to the input element’s value.

```jsx
class MyForm extends React.Component {
  constructor(props) {
    super(props);
    this.inputRef = React.createRef();
  }

  handleSubmit = (event) => {
    alert('A name was submitted: ' + this.inputRef.current.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" ref={this.inputRef} />
        </label>
        <button type="submit">Submit</button>
      </form>
    );
  }
}
```

**2. Access Form Values on Submission:** Since the form is uncontrolled, you can access the input value directly from the DOM using the ref in the form submission handler, rather than relying on state.

**Advantages of Uncontrolled Components**

Simplicity: For simple forms or when integrating with non-React code, uncontrolled components can be simpler to implement.
Performance: Reduces the number of re-renders since input updates do not trigger state changes.

**When to Use Uncontrolled Components**

Uncontrolled components are best used in situations where you do not need to track the form input's value in the React component's state. They are particularly useful for:

1. Simple forms that do not require real-time validation or feedback.
2. Integrating with non-React code that relies on direct DOM manipulation.
3. Performance optimization in very large forms where minimizing re-renders is critical.

**Conclusion**

While uncontrolled components might seem counterintuitive in React's declarative paradigm, they serve specific use cases by offering a straightforward and performant way to handle form inputs. Understanding when and how to use uncontrolled components effectively is a valuable skill in React development.


<br/>

**2. Controlled way of handling forms in React?**

**Answer:**

**Controlled components** in React are those where the React component controls the state of the input fields. In this approach, form data is handled by the state within the component, making the React state the "single source of truth" for all input elements.

**How Controlled Components Work:**

In controlled components, the value of each input field is controlled by React state, and any changes to that value are handled by event handlers (`onChange`), which update the state accordingly.

**Implementing Controlled Components:**

To implement a controlled component in React:

1. **Bind Input Values to State**: Each input's value is set by the component's state.

```jsx
class MyForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = { value: '' };
  }

  handleChange = (event) => {
    this.setState({value: event.target.value});
  }

  handleSubmit = (event) => {
    alert('A name was submitted: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
        </label>
        <button type="submit">Submit</button>
      </form>
    );
  }
}
```

2. **Handle Changes with Event Handlers:** Use the onChange event to capture input changes and update the state, which in turn updates the input field's value.

**Advantages of Controlled Components:**

Consistency: The React state acts as a single source of truth, ensuring UI consistency.
Integrated Validation: Easy to integrate real-time validation as the input value is always accessible through the component's state.
Form Submission: The form submission process can be fully controlled with React, allowing for more complex behaviors like preventing default form submission if validation fails.

**When to Use Controlled Components:**

Controlled components are particularly useful when:

1. You need to implement real-time validation as the user types or before submission.
2. The form's input data needs to be integrated with other UI elements in your application.
3. You are building complex forms that require dynamic inputs or other interactive features.

**Conclusion**

Controlled components offer a powerful way to manage form input values in React. By leveraging the component's state to control input values and handle changes, developers can create more dynamic, responsive, and user-friendly forms. This approach aligns with React's philosophy of using state to manage UI data, providing a coherent and predictable way to build form-heavy applications.

<br/>

**3. What are the 5 Steps to Design a React Component?**

**Answer:** Designing React components efficiently is crucial for building scalable and maintainable applications. Here's a step-by-step guide to help you design React components effectively:

**1. Identify The Component's Purpose**

   - **Define Functionality**: Determine what the component is supposed to do. Understand its role within the application, whether it's presenting data, handling user input, or encapsulating a specific functionality.
   - **Single Responsibility Principle**: Ensure the component has a single responsibility and encapsulates only one aspect of the UI. If a component does too many things, consider breaking it down into smaller components.

**2. Decide on The Data Flow**

   - **Props vs. State**: Determine what data the component will manage internally (state) and what data will be passed to it from parent components (props). This helps in understanding the component's dependency and its reusability.
   - **Data Fetching**: Decide where the data fetching should occur if the component needs data from an API. Often, data fetching is handled by higher-level components or using custom hooks.

**3. Plan Out The Component Structure**

   - **Component Hierarchy**: Sketch out the component hierarchy if your component will be composed of sub-components. Identify how components will communicate with each other, especially how data and callbacks will be passed through props.
   - **Reusable Components**: Identify opportunities to abstract common UI elements into reusable components. This reduces duplication and increases the consistency of your application.

**4. Implement The Component**

   - **Choose a Type**: Decide whether the component will be a class component or a functional component. With the introduction of Hooks, functional components can now manage state and side effects, making them a preferred choice for most cases.
   - **Write JSX**: Start coding your component by writing JSX for the UI. Focus on the structure first, without worrying too much about the styling details.
   - **State Management**: Implement state management within your component if necessary. Use hooks like `useState` and `useEffect` for managing local state and side effects in functional components.
   - **Event Handlers**: Add event handlers to your component to handle user interaction, such as clicks and form submissions.

**5. Test and Refine**

   - **Unit Tests**: Write unit tests for your component to ensure it behaves as expected. Testing frameworks like Jest and testing utilities like React Testing Library are commonly used.
   - **Performance Optimization**: Optimize your component for performance. Use React's optimization techniques such as memoization with `React.memo`, lazy loading with `React.lazy`, and avoiding unnecessary re-renders.
   - **Review and Refactor**: Review your component's design and implementation. Refactor if necessary to improve readability, efficiency, or maintainability.

**Conclusion**
            
Designing a React component involves a thoughtful process of planning, implementation, and testing. By following these steps, you can create components that are clear in purpose, easy to maintain, and reusable across your application. This not only improves the quality of your application but also enhances the development experience.


<br/>

**4. Grouping Data in React: Object vs. Array?**

**Answer:** When designing React components and managing state, choosing between objects and arrays for grouping data is crucial. Here's how to decide:

1. When to Use an Array

   - **Ordered List of Items**: Use an array when you have a collection of items where order matters. Arrays are ideal for lists of elements that will be rendered using `.map()` to create components like a list of messages, tasks, or search results.

   - **Iteration**: If you need to iterate over the data frequently to render elements or perform operations like `.map()`, `.filter()`, or `.reduce()`, an array is the preferred choice.

   - **Homogeneous Items**: Arrays are well-suited for collections of items of the same type, where each item follows the same structure or set of data fields.

      **Example Usage**:
      ```jsx
      const [todos, setTodos] = useState([
        { id: 1, text: 'Learn React', completed: false },
        { id: 2, text: 'Build a project', completed: false },
      ]);
      ```
     
2. When to Use an Object
   - Key-Value Pairs: Use an object when you need to store data in key-value pairs where each key has a specific meaning or reference, such as configurations, user profiles, or settings. 
   - Lookup by Key: Objects are ideal for scenarios where you need to lookup items directly by a key without iterating over the entire collection, providing efficient access to elements. 
   - Heterogeneous Data: Objects are suitable for grouping related but different types of data about a single entity, where each key can represent a different aspect of the data.

   **Example Usage:**

   ```jsx
   const [userProfile, setUserProfile] = useState({
   username: 'reactuser',
   email: 'user@example.com',
   preferences: { theme: 'dark', notifications: true },
   });
   ```
   
**Best Practices:**

1. Consistency: Choose a data structure that matches the nature of your data and stick with it across your application for consistency. 
2. Immutability: Whether using objects or arrays, always treat them as immutable in React state. Use functions like setState, ...spread operator, or utilities like Array.prototype.map() for updates to ensure components re-render correctly. 
3. Normalization: For complex datasets, consider normalizing your state. This might involve using a combination of objects for efficient data lookup and arrays to maintain order or lists of keys.

**Conclusion**

The decision to use an object or an array in React state largely depends on the data's structure and intended use. Arrays are best for ordered collections and iteration, while objects are suited for keyed data and direct access. By understanding the strengths and use cases of each, you can effectively manage state in your React applications.

<br/>

### 3.4 Choosing the State Structure - Group related state

<br/>

### 3.5 Choosing the State Structure - Avoid contradictions in state

<br/>

### 3.6 Choosing the State Structure - Avoid redundant state

<br/>

### 3.7 Choosing the State Structure - Avoid duplication in state

<br/>

### 3.8 Choosing the State Structure - Avoid deeply nested state

<br/>

### 3.9 Sharing State Between Components - Lifting state up

<br/>

### 3.10 Preserving and Resetting State - Default behavior

<br/>

### 3.11 Resetting state at the same position - Changing Default behavior

<br/>

### 3.12 Extracting State Logic into a Reducer - Example project

<br/>

### 3.13 Three steps to Consolidate state logic with a reducer

<br/>

### 3.14 Comparing useState and useReducer - How to write reducers well

<br/>

### 3.15 Writing concise reducers with Immer

<br/>

### 3.16 Passing Data Deeply with Context - Introduction to Context API

<br/>

### 3.18 Context passes through intermediate components

<br/>

### 3.19 Some notes and use cases for Context

<br/>

### 3.20 Scaling Up with Reducer and Context

<br/>

### 3.21 Project Tutorial - CineRental: Your One-Stop React App for Movie Magic and Rentals

<br/>

### Assignment 3 Requirements - Improved Tasker



