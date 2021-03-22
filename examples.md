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

### Compound components

```
<Select
  value={value}
  onChange={handleChange}
  options={[
    { value: "apple", label: "Apple" },
    { value: "pear", label: "Pear" }
  ]}
/>;

```

```
<Select value={value} onChange={handleChange}>
  <Select.Option value="apple">Apple</Select.Option>
  <Select.Option value="pear">Pear</Select.Option>
</Select>;
```

https://www.uxpin.com/studio/blog/react-design-patterns/

https://egghead.io/lessons/react-write-compound-components

https://blog.logrocket.com/guide-to-react-compound-components-9c4b3eb482e9/

https://codesandbox.io/s/react-compound-pattern-73rx6?from-embed
