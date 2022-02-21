##### 初始化项目

npx create-react-app my-app

##### 启动项目

在根目录中  npm start

#### 创建react元素

##### 使用jsx语法创建react元素

```jsx
const title = (<h1>Hello JSX</h1>)
```

#### 注意

- React 元素的属性名采用驼峰命名法
- 特殊属性名 ：class ->className、for -> htmlFor 、tabindex->tabIndex
- 没有子节点的React元素可以用 />结束
- 推荐 使用小括号()包裹JSX

#### 渲染react元素

- 参数一 ：要渲染的react元素

- 参数点： 挂载点

  ```jsx
  ReactDOM.render(title,document.getElementById('root')) 
  ```

#### 嵌入js

- 放在单大括号中{}

- jsx也是js表达式

- js中的对象是一个例外，一般只会出现在style属性中

- 不能在{}中出现语句比如if/for等

  ```jsx
  const name = 'qweqweq' //可以是字符
  const name = <div>我是一个div</div> //可以是jsx
   const sayHi = (yu) =>"'hi~'+yu"//可以是函数表达式
  const title = <h1 className='title'>helllloooooo {name}
          		<p>{sayHi(lk)}</p>
  </h1>
  ```

#### jsx条件渲染

一般用于实现加载效果 ，可以用if/else 、三元运算符和逻辑运算 例如&&

```jsx
const  isloading = true;
//函数
const load =()=>{
  return isloading ? 'asdasd' : 'qwe'
}
//创建react
const title = <h1>{load()}</h1>

//渲染react
ReactDOM.render(title,document.getElementById('root'))
```

#### jsx列表渲染

```jsx

const people = [
  {id : 1, name :'qq'},
  {id : 2, name :'ww'},
  {id : 3, name :'ee'}
]
//创建react
const title = <ul>{people.map(item => <li key={item.id}> {item.name} </li>)}</ul>

//渲染react
ReactDOM.render(title,document.getElementById('root'))
```

#### jsx的样式处理

##### 使用className 在css中写入样式

```jsx
//创建react
const title = (<h1 className="title">wertyu</h1>)
```

