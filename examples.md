### Render Props
```
const Wrapper =() => {
  const [counter, setCounter] = useState(0)

  // Increase count
  increment = () => {
    setCounter(count + 1 );
  };

  // Decrease count
  decrement = () => {
    setCounter(count - 1);
  };
  
    return (
      <div>
        {this.props.render({
          increment: this.increment,
          decrement: this.decrement,
          count: count
        })}
      </div>
    );
}
```
```
const App = () => {
    return (
      <Wrapper
        render={({ increment, decrement, count }) => (
          <div>
            <div>
              <h3>Render Props Counter</h3>
            </div>
            <div>
              <p>{count}</p>
              <button onClick={() => increment()}>Increment</button>
              <button onClick={() => decrement()}>Decrement</button>
            </div>
          </div>
        )}
      />
    );
  }
```

### Higher order components

```
const hoc = (WrappedComponent) => (props) => {
  return (
    <div>
      <WrappedComponent {...props}>
        {props.children.toUpperCase()}
      </WrappedComponent>
    </div>
  )
}
```


```
const Username = (props) => (
  <div>{props.children}</div>
)
```

```

const UpperCaseUsername = hoc(Username)

const App = () => (
  <div>
    <UpperCaseUsername>Kingsley</UpperCaseUsername>
  </div>
);
```

### Dependency Injection
```

```

