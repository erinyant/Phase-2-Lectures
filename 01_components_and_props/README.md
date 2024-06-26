# Components & Props

<h2> 🚗 React Roadmap

The goals for Phase 2: </h2>

- Create a static frontend site with components and props (DOM Manipulation)

- Use state and events to make your site dynamic (Event Handling)

- Add side effects and data fetching to communicate with a server (Network Communication)

### SWBATs:

- [ ] Review the benefits of React over Vanilla JS
- [ ] Review the difference between HTML and JSX
- [ ] Review the importance of Components
- [ ] Review how a component is written
- [ ] Explain what props are and how to create them
- [ ] Recognize destructured props and how to work with them
- [ ] Recognize best practices when writing components and props
- [ ] Observe how to render multiple components from a list

### Creating a React App

`create-react-app` will build a project folder for our application and install all the dependencies we need (via Node Package Manager).

To create a new React application and start it, run:

```
npx create-react-app app-name
cd app-name
npm start
```

In addition to React, it gives us:

- Webpack: a tool for bundling and minifying our code (along with a server for running our code in development)
- Babel: a transpiler that lets us write modern JavaScript and JSX

<h2> React > Vanilla JS </h2>

Instead of describing how to do something:

```js
const h1 = document.createElement("h1");
h1.id = "main";
h1.className = "blue";
h1.textContent = "Hello!";
```

We can just describe what we want:

```js
const h1 = (
  <h1 id="main" className="blue">
    Hello from JSX!
  </h1>
);
```

<!-- slide -->

<h2> ⚙️ Components </h2>

<p>

Components are the building blocks of React. A component is a function that:

- Takes in some raw data (props)
- Returns user interface (JSX)

</p>

```js
const Header = () => {
  return (
    <div>
      <h3>Hello World</h3>
    </div>
  );
};

ReactDOM.render(<Header />, document.getElementById("root"));
```

<!-- slide -->

<h2> ⚙️ Component Gotchas </h2>

This is okay:

```js
function Card() {
  return (
    <div id="card1" className="card">
      <h1>hi</h1>
      <p>wassup?</p>
    </div>
  );
}
```

This is NOT okay:

```js
function card() {
  return (
    <h1>hi</h1>
    <p>wassup?</p>
  )
}
```

- Component name needs to be capitalized
- Components can only return one element

<!-- slide -->

<h2> 🎩 Props! </h2>

When you create components, one way to make them dynamic and reusable is by passing in props. For example, if we wanted to create several cards on our page using a Card component, we could do so like this:

```js
function Card(props) {
  return (
    <div id="card1" className="card">
      <h1>{props.greeting}</h1>
      <p>{props.subGreeting}</p>
    </div>
  );
}

// Inside another component

return (
  <div>
    <Card greeting="hi" subGreeting="hello" />
    <Card greeting="sup" subGreeting="what's up" />
  </div>
);
```

<!-- slide -->

<h2> 🎩 Props Continued </h2>

The props argument in our Card component defines an object that React will pass to our function when it is called, and it will use whatever attributes we add to our JSX component as key-value pairs on that props object.

For example, if we were to add a console.log in the Card component above, we'd end up seeing this object:

```js
function Card(props) {
  console.log(props); // => { greeting: "hi", subGreeting: "hello" }

  return (
    <div id="card1" className="card">
      <h1>{props.greeting}</h1>
      <p>{props.subGreeting}</p>
    </div>
  );
}
```

<!-- slide -->

<h2> Wireframes </h2>

<img src="https://res.cloudinary.com/dnocv6uwb/image/upload/v1643721399/wireframe_bfc35e.png">


### Deliverables

#### 1. Create an `App` component that:

- Returns the `Header`, `ProjectForm` and `ProjectList` components

- Provides the array of `projects` to `ProjectList` as props

#### 2. Create a `header` component that:

- Renders the text `Header`

#### 3. Create a `ProjectForm` component that:

- Renders the text `ProjectForm`

#### 4. Define a `ProjectList` component that:

- Accepts the props provided to the component

- Destructures `projects` from the props object

- Maps over the `projects` array to render the `ProjectListItem` component for each element:

  - Provide a key prop set to the `project id` value

  - Provide each `project` object as a prop named `project`

#### 5. Define a `ProjectListItem` component that:

- Accepts the props argument

- Destructure the props object and return `project`

- Destructure the properties of the `project` object

- Create an `img` element nested inside a `figure` element

- Set the `img` property `src` to the `img` variable created when destructuring

- Set the `img` property `alt` to `project: ${name}`

- Create an `article` element with `h4` and `p` tags nested inside

  - Dynamically render each project name inside the `h4` tag

  - Dynamically render each project's about data inside the `p` tag
- Create a `footer` element with a `span` inside that renders the phase

### Resources

- [React](https://reactjs.org/)
- [Babel](https://babeljs.io/)
- [Creating React Apps](https://reactjs.org/docs/create-a-new-react-app.html)
- [create-react-app](https://create-react-app.dev/docs/getting-started)
- [Webpack](https://webpack.js.org/)
- [Quick intro to Webpack](https://medium.com/the-self-taught-programmer/what-is-webpack-and-why-should-i-care-part-1-introduction-ca4da7d0d8dc)

### VSCode extensions

- [draw.io integration](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Tabnine](https://marketplace.visualstudio.com/items?itemName=TabNine.tabnine-vscode)
- [ES7+ React/Redux/React-Native/JS snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
