## react组件实例

### 实现步骤

- ##### 先实现核心功能，再考虑边界问题

1. 给按钮绑定单击事件
2. 在事件处理程序中，通过state获取评论信息
3. 将评论信息添加到state中，并调用setState（）方法更新state
4. 边界情况：清空文本框
5. 边界情况：非空判断



```jsx
class App extends React.Component{
  //初始化状态
  state = {
    comments:[
      { id : 1, name : "jack", content :'111'},
      { id : 2, name : "jacak", content :'11111'},
      { id : 3, name : "jasck", content :'11332'},
    ],
    // 评论人
    userName: '',
    // 评论状态
    userContent: ''
  }
  // 渲染评论列表
  renderList(){
    return    this.state.comments.length === 0
    ?(<div className='no-comment'>暂时没有评论哦</div>)
    :( <ul>
    {
      this.state.comments.map(item =>(
        <li key= {item.id}>
          <h3>评论人：{ item.name}</h3>
          <p>评论内容：{item.content}</p>
        </li>
      ))
    }
   </ul>)
  }
// 处理表达元素值
   onchange1= e =>{ 
     const {name , value} = e.target
     this.setState({
       [name]: value
     })
   }
  //  添加评论
   addComment = ()=>{
     const  {comments, userName,userContent} = this.state
  //  非空校验
     if(userName.trim()==='' || userContent.trim()=== ''){
       alert('输入内容')
       return //不继续执行
     }

     const newComments = [{
      id : Math.random(),
      name: userName,
      content : userContent
     },...comments]
     this.setState({
       comments: newComments,
       userName : '',
       userContent : ''
     })
   }
  render(){
    const {userName,userContent}= this.state
    return(
      <div className='app'>
        <div className='app'>

        <input className='user' type="text" 
        placeholder="请输入内容" 
        value={userName}
        name = 'userName'
        onChange = {this.onchange1}
        ></input>
        
        <textarea className='content' 
        cols = '30' rows = '10' 
        placeholder = '请输入内容' 
        value= {userContent}
        name = 'userContent'
        onChange = {this.onchange1}
        ></textarea>

        <button onClick = {this.addComment}>发表评论</button>

        </div>
        {/* 通过条件渲染决定渲染什么内容 */}
     {this.renderList()}   
      </div> 
    )
  }
}
ReactDOM.render(<App/>,document.getElementById('root'))
```

