<img src="img/react.svg" class="spin logo logo--small" />

### Setting up a barebones React project from scratch

[Link to the repo](https://github.com/react-sessions/react-barebones)

---

- First, set up an [html template](https://drive.google.com/open?id=0B7CIzG7rTeYiczYyX210eURxTDA)
- This includes our React root and our script tag to include
 the script created by Webpack

---

### Install React and ReactDOM

- (optionally) Install yarn package manager

    ```
    npm i -g yarn
    ```

- Install `react` and `react-dom`

    ```
    yarn add react react-dom
    ```

---

### Install webpack and webpack-dev-server for bundling

```
yarn add --dev webpack webpack-dev-server
```

---

### Create [webpack config](https://drive.google.com/open?id=0B7CIzG7rTeYiUVR2VXQ5UWRoTk0)

---

### Install babel (and presets) for transpilation

```
yarn add --dev babel-core babel-loader babel-preset-env babel-preset-react
```

---

### Create a .babelrc file to pass in the presets

```
{
    "presets": [
        "env", "react"
    ]
}
```
