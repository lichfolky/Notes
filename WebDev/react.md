## Best practices
```
{condition && <p>The condition must be true!</p>}
```
```
{condition ? (
       <p>The condition must be true!</p>
     ) : (
       <p>The condition must be false!</p>
     )}
```
```
import React from 'react'

const HungryMessage = ({ isHungry }) => (
  <span>{isHungry ? 'I am hungry' : 'I am full'}</span>
)

export const BooleanPropGood = () => (
  <div>
    <span>
      <b>This person is hungry: </b>
    </span>
    <HungryMessage isHungry />
    <br />
    <span>
      <b>This person is full: </b>
    </span>
    <HungryMessage isHungry={false} />
  </div>
)
```

```
const handleChange = e => {
  setInputValue(e.target.value)
}
...
<input id="name" value={inputValue} onChange={handleChange} />
```
### passing a component as a prop to another component
```
import React from 'react'

const CircleIcon = () => (
  <svg height="100" width="100">
    <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="red" />
  </svg>
)

const ComponentThatAcceptsAnIcon = ({ IconComponent }) => (
  <div>
    <IconComponent />
  </div>
)

export const UnnecessaryAnonymousFunctionComponentsGood = () => (
  <ComponentThatAcceptsAnIcon IconComponent={CircleIcon} />
)
```

### Undefined props are excluded, so don’t worry about providing an undefined fallback
```
import React from 'react'

const ButtonOne = ({ handleClick }) => (
  <button onClick={handleClick}>Click me</button>
)

export const UndefinedPropsGood = () => (
  <div>
    <ButtonOne />
    <ButtonOne handleClick={() => alert('Clicked!')} />
  </div>
)
```
