## react组件通讯

#### 组件的props

- 组件是封闭的，要接受外部数据应该通过props来实现
- props的作用：接受传递给组件的数据
- 传递数据：给组件标签添加属性
- 接受数据：函数租金啊通过参数props接受数据，类组将通过this.props接受数据

### 组件props的特点

- 可以给组件传递任意类型的数据
- props 是只读的对象，只能读取属性的值，无法修改对象
- 使用类组件时，如果写了构造函数，应该将props传递给super()，否则，无法在构造函数中获取到props

### 类组件

```jsx
class Hello extends React.Component{
  render(){
    return (
      <div>接受到的数据：{this.props.ages}</div>
    )
  }
}
 reactDom.render(<Hello ages={12}></Hello>, document.getElementById('root'))
```

### 函数组件

```jsx
function Helo(props){
   console.log(props);
   return (
     <div>接受到的数据：{props.ages}</div>
   )
 }
 ReactDOM.render(<Helo name='asd' ages={2} ></Helo>,document.getElementById('ddv')) 
```