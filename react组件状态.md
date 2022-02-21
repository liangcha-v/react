### 有状态组件和无状态组件

- 函数组件叫做无状态组件，类组件又叫有状态组件
- 状态 state 即数据
- 函数组件没有自己的状态，只负责数据展示（静）
- 类组件有自己的状态，负责更新ui，让页面动起来

### 组件中的state和 setState

##### state 的基本使用

- 状态（state）即数据，是组件内部的私有数据，只能在组件内部使用
- state 的值是对象，表示一个组件中可以有多个数据

##### setState()修改状态

- 状态是可变的
- 语法： this.setState({要修改的数据})
- 不要直接修改state的中的值，这是错误的   this.state.count + = 1 //错误
- setState()作用： 1.修改state  2.更新UI

```jsx
class Hello extends React.Component{
state={
  count: 0
}
  render(){
    return(
      <div><h1>计数器 {this.state.count+1}</h1>
      <button onClick={()=>{
        this.setState({
          count:this.state.count+1
        })
      }}>点我呀</button>
      </div>
    )
  }
}
ReactDOM.render(<Hello></Hello>,document.getElementById('root'))
```

### 事件绑定this指向

- 使用class实例方法

  ```jsx
  class Hello extends React.Component{
    handleClick= () =>  {
      // console.log('真点了');
      this.setState({
        count:this.state.count+1
      })
    }
  state={
    count: 0
  }
    render(){
      return(
        <div><h1>计数器 {this.state.count+1}</h1>
        <button 
        // onClick={()=>{
        //   this.setState({
        //     count:this.state.count+1
        //   })
        // }}
        onClick={this.handleClick}
        >点我呀</button>
        </div>
      )
    }
  }
  
  ReactDOM.render(<Hello></Hello>,document.getElementById('root'))
  ```

## 

