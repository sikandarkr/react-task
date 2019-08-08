# react-task

##1.
  The following component is printing list of item.
##2.
   a)Improvement:-we can use super keyword to access the prop from parent class.
    b)we can import component from 'react'  like import React,{Component} from 'react' so that we don't have to write        React.Component.
 c)we can have state without constructor also.
```
import React from 'react'

class SomeListComponent extends React.Component {
  constructor (props) {
    this.state = { items: props.items }
  }

  shouldComponentUpdate (nextProps) {
    return nextProps.items !== this.props.items
  }

  handleClick (index) {
    this.props.onClick(index)
  }

  renderElement (item, index) {
    return <li onClick={() => this.handleClick(index)}>{item.text}</li>
  }

  render () {
    return (
      <ul style={{ backgroundColor: 'red', height: 100 }}>
        {this.state.items.map((item, i) => this.renderElement(item, i))}
      </ul>
    )
  }
}

export default SomeListComponent

```
