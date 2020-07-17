<div align="center">
    <h1 align="center">DEPRECATED</h1>
    <p align="center">
        🚨 Hey, this repository is DEPRECATED and will no longer be actively maintained!
    </p>
</div>


<br />
<br />
<br />
<br />
<br />

## RocketNative Snippets

React Native code snippets for Atom

## Summary

- [Installation](#installation)
- [Usage](#usage)
    - [Component](#component)
    - [ESLint](#eslint)
    - [Redux](#redux)
    - [Reactotron](#reactotron)
    - [Babel](#babel)
    - [Apisauce](#apisauce)

![Demo](https://raw.githubusercontent.com/frankyston/rocketnative-atom-snippets/master/demo.gif)

### Installation
To add your own snippets, select the _Atom > Snippets..._ menu option if you're using macOS, or the _File > Snippets..._ menu option if you're using Windows, or the _Edit > Snippets..._ menu option if you are using Linux.

Copy the contents of the `snippets.cson` file and paste it into the file opened by atom or open the file manually in the folder `~/.atom/snippets.cson`.

## Usage
### Component
#### [component] - Create react-native component
```javascript
/* Core */
import React, { Component } from 'react';

/* Presentational */
import { View } from 'react-native';

// import styles from './styles';

export default class MyComponent extends Component {
  render() {
    return (
      <View />
    );
  }
}
```

#### [proptypes] - Create component propTypes
```javascript
static propTypes = {

};
```

#### [defaultprops] - Create component defaultProps
```javascript
static defaultProps = {

};
```

#### [render] - Create render method
```javascript
render() {
  return (
    <View />
  );
}
```

### ESLint
#### [eslint] - Create eslint file config
```json
{
  "parser": "babel-eslint",
  "env": {
    "browser": true,
    "jest": true
  },
  "plugins": [
    "react-native",
    "jsx-a11y",
    "import"
  ],
  "extends": [
    "airbnb",
    "plugin:react-native/all"
  ],
  "rules": {
    "react/jsx-filename-extension": ["error", { "extensions": [".js", ".jsx"] }],
    "global-require": "off",
    "no-console": "off",
    "import/prefer-default-export": "off",
    "no-unused-vars": ["error", {"argsIgnorePattern": "^_"}]
  },
  "settings": {
    "import/resolver": {
      "babel-module": {}
    }
  },
  "globals": {
    "__DEV__": true
  }
}
```

### Redux
#### [setupredux] - Create Redux Setup file
```javascript
import { combineReducers } from 'redux';

/* Reducers */
// import navReducer from 'navigation/reducer';

import configureStore from './configureStore';
// import rootSaga from './sagas';

export default () => {
  const rootReducer = combineReducers({
    // nav: navReducer,
  });

  return configureStore(rootReducer, rootSaga);
};
```

#### [configureStore] - Create configureStore file
```javascript
import { createStore, applyMiddleware, compose } from 'redux';

export default (rootReducer) => {
  const middleware = [];
  const enhancers = [];

  /* Saga */
  // const sagaMonitor = __DEV__ ? console.tron.createSagaMonitor() : null;
  // const sagaMiddleware = createSagaMiddleware({ sagaMonitor });
  // middleware.push(sagaMiddleware);

  enhancers.push(applyMiddleware(...middleware));

  /* Store */
  const createAppropriateStore = __DEV__ ? console.tron.createStore : createStore;
  const store = createAppropriateStore(rootReducer, compose(...enhancers));

  /* Run Saga */
  // sagaMiddleware.run(rootSaga);

  return store;
};
```



#### [mapStateToProps] - Create redux mapStateToProps
```javascript
const mapStateToProps = state => ({

});
```

#### [mapDispatchToProps] - Create redux mapDispatchToProps
```javascript
const mapDispatchToProps = dispatch => ({

});
```

### Reactotron
#### [reactotronconfig] - Create Reactotron Config
```javascript
import Reactotron from 'reactotron-react-native';

if (__DEV__) {
  const tron = Reactotron
    .configure()
    .useReactNative()
    .connect();

  tron.clear();

  console.tron = tron;
}
```

### Babel
#### [moduleResolver] - Create Module Resolver config
```json
"plugins": [
  [
    "module-resolver",
    {
      "root": ["./src"],
      "extensions": [".js", ".ios.js", ".android.js"]
    }
  ]
]
```

### Apisauce
#### [apisauce] - Create APISauce Config
```javascript
import { create } from 'apisauce';

const api = create({
  baseURL: 'http://localhost:3000',
});

export default api;
```
