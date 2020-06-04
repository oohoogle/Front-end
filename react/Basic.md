# React Basic

### 1. JSX

+ 클래스형 컴포넌트

```javascript

import React from 'react';
import './App.css';

function App() {
    const name = '리액트';
    return <div className="react">{name}</div>
}

export default App;
```