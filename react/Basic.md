# React Basic

### 1. JSX

+ 함수형 컴포넌트

```javascript

import React from 'react'; // 리액트를 불러와서 사용할 수 있게 해준다.
import './App.css';

function App() {
    const name = '리액트';
    return <div className="react">{name}</div>
}

export default App;
```

+ 클래스형 컴포넌트

```javascript
import React, { Component } from 'react';

class App extends Component {
    render(){
        const name = 'react'
        return <div className="react">{name}</div>
    }
}
export default App;

```