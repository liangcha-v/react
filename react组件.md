### 组件创建

#### 函数创建组件

- 使用js的函数创建的的组件

- 函数名必须以大写字母开头

- 函数组件必须有返回值，表示该组件的结构

  ```jsx
  //函数组件
  function Hello(){
    return (
      <div>qwerty</div>
    )
  }
  reactDom.render(<Hello></Hello>,document.getElementById('ddiv'))
  ```

#### 使用类创建组件

- 类名称必须以大写字母开头
-  类组件应该继承React.Component 父类，从而可以使用父类提供的方法或属性
- 类组件必须提供render()方法
- render()方法必须有返回值，表示该组件的结构

```jsx
//创建类组件
class Helll extends React.Component{
  render(){
    return(
      <div>类组件</div>
    )
  }
}
//渲染类组件
reactDom.render(<Helll></Helll>,document.getElementById('divv'))
```

## 分离组件在不同的js中

####  Helll.js中

```jsx
//创建类组件
class Helll extends React.Component{
  render(){
    return(
      <div>类组件</div>
    )
  }
}
//导出组件
export default Helll
```

#### index.js中

```jsx
//导入Helll组件
import Helll from './Helll'
//渲染组件
reactDom.render(<Helll></Helll>,document.getElementById('divv'))
```

