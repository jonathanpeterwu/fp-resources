# Functional Reactive Programming Resources
Reference Guides and resources to learn functional programming


#### FRP Resources
 [Intro to FP](https://www.hackerrank.com/challenges/fp-solve-me-first)
 
 [Intro to Functional Reactive Programming](https://github.com/Reactive-Extensions/RxJS)
 
 [RxJS (Observables) source](https://github.com/Reactive-Extensions/RxJS/blob/master/doc/libraries/lite/rx.lite.md)

#### Elm Resources
 [Try Elm](http://elm-lang.org/try)


#### Om Resources (focused on Om.next)
 [Quick Start Guide](https://github.com/omcljs/om/wiki/Quick-Start-(om.next))

#### Clojure Resources
 [JUXT Training Courses](https://juxt.pro/training.html)

#### Clojurescript Resources

### React Redux Resources
 [React Router Binding w/ Redux](https://github.com/rackt/react-router-redux)
 [Redux Router](https://github.com/acdlite/redux-router)
 
 Example setup
 ```
 import React from 'react'
import ReactDOM from 'react-dom'
import { createStore, combineReducers, applyMiddleware } from 'redux'
import { Provider } from 'react-redux'
import { Router, Route, browserHistory } from 'react-router'
import { syncHistory, routeReducer } from 'react-router-redux'
import reducers from '<project-path>/reducers'

const reducer = combineReducers(Object.assign({}, reducers, {
  routing: routeReducer
}))

// Sync dispatched route actions to the history
const reduxRouterMiddleware = syncHistory(browserHistory)
const createStoreWithMiddleware = applyMiddleware(reduxRouterMiddleware)(createStore)

const store = createStoreWithMiddleware(reducer)

// Required for replaying actions from devtools to work
reduxRouterMiddleware.listenForReplays(store)

ReactDOM.render(
  <Provider store={store}>
    <Router history={browserHistory}>
      <Route path="/" component={App}>
        <Route path="foo" component={Foo}/>
        <Route path="bar" component={Bar}/>
      </Route>
    </Router>
  </Provider>,
  document.getElementById('mount')
)
 ```
 
