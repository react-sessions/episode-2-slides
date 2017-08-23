<img src="img/react.svg" class="spin logo logo--small" />

## Setting up a React project

---

Setting up a basic project can be a daunting task, where do you start? How do you setup and configure Webpack? Babel? ESLint?

Once they are set up how do you manage and test package updates?

------

### Enter: Create React App

> “Create React apps with no build configuration.”

[<small>github.com/facebookincubator/create-react-app</small>](https://github.com/facebookincubator/create-react-app)

---

#### Officially supported as a way to create single-page React applications

---

## Philosophy

---

### One Dependency

> There is just one build dependency. It uses Webpack, Babel, ESLint, and other amazing projects, but provides a cohesive curated experience on top of them.

---

### No Configuration Required

> You don't need to configure anything. Reasonably good configuration of both development and production builds is handled for you so you can focus on writing code.

---

### No Lock-In

> You can “eject” to a custom setup at any time. Run a single command, and all the configuration and build dependencies will be moved directly into your project, so you can pick up right where you left off.

------

## Creating a `create-react-app` project

---

### Install globally

```bash
yarn global add create-react-app
```

Or

```bash
npm i create-react-app -g
```

---

### Create a new app

```bash
create-react-app my-app

cd my-app/
```

A directory called my-app will be created with the initial project structure along with the basic files required to build an application.

---

```
my-app
├── README.md
├── node_modules
├── package.json
├── .gitignore
├── public
│   └── favicon.ico
│   └── index.html
│   └── manifest.json
└── src
    └── App.css
    └── App.js
    └── App.test.js
    └── index.css
    └── index.js
    └── logo.svg
    └── registerServiceWorker.js
```

---

### Run the app

```bash
yarn start
```

The app will run at http://localhost:3000

---


### Building for Production

```bash
yarn build
```

Creates an optimized bundle for production.

---

### Testing

```bash
yarn test
```

Watches your code and test files for changes using Jest.

When changes are made the related tests are run.

---

### Ejecting

```bash
yarn eject
```

“Ejecting” lets you leave the comfort of Create React App setup at any time. You run a single command, and all the build dependencies, configs, and scripts are moved right into your project.

Note that this is a one way operation, it cannot be undone!

------

## Honourable mentions

---

### [zeit/next.js](https://github.com/zeit/next.js)

- Server-rendered by default
- Automatic code splitting for faster page loads
- Simple client-side routing (page based)
- Webpack-based dev environment which supports Hot Module Replacement(HMR)
- Able to implement with Express or any other Node.js HTTP server
- Customizable with your own Babel and Webpack configurations

---

[StackBlitz](https://stackblitz.com/fork/react)

- Online VS Code IDE
- Intellisense, Project Search (Cmd/Ctrl+P), Go to Definition, and other key VS Code features
- Hot reloading as you type
- Import NPM packages into your project
- Keep editing while offline thanks to our revolutionary in-browser dev server
- Hosted app URL where you can see (or share) your live application at any time
