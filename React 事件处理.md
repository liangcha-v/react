## 事件绑定

- 语法 ： on + 事件名称 = {事件处理程序}， 比如 onClick = {()=>()}
- 注意：React事件采用驼峰命名法， 比如onMouseEnter、onFocus
- 在函数中绑定事件

#### 类组件中放入事件

```jsx
//类组件
class Helll extends React.Component{
  handleClick(){
    console.log('真点了');
  }
  render(){
    return(
      <button onClick={this.handleClick}>点我呀</button>
    )
  }
}
//渲染类组件
reactDom.render(<Helll></Helll>,document.getElementById('divv'))
```

#### 函数组件中放入事件

```jsx
//函数组件
function Hello(){
  function handleClick(){
    console.log("别点了");
  }
  return (
    <button onClick={handleClick}>点击</button>
  )
}
//渲染组件
reactDom.render(<Hello></Hello>,document.getElementById('ddiv'))
```

