## 表单的基本操作

1. form 标签：表单容器

   action 属性：向后台提交数据

2. label 标签：用来描述输入框

   for 属性：默认是空（对应输入框的 id，点击 label 文本时会自动 focus 到输入框）

   ```html
   <label for="username">用户名</label>
   ```

3. input 标签:

   placeholder 属性: 显示默认的提示信息

   type 属性：

   - text 文本输入框

     ```html
     <input id="username" type="text" placeholder="用户名" />
     ```

   - password 密码输入框（不可见）

     ```html
     <input id="password" type="password" placeholder="密码" />
     ```

   - submit 按钮（默认：提交）

     ```html
     <input type="submit" value="登录" />
     ```

   - button 纯按钮

     ```html
     <input type="button" value="按钮" />
     ```

   - radio 单选框

     name 属性：把两个 radio 绑定到 name，就可以避免两个都选，做到只能选其中一个

     ```html
     <label>男</label>
     <input name="sex" type="radio" />
     <label>女</label>
     <input name="sex" type="radio" />
     ```

   - checkbox 复选框

4. select 标签：下拉框

   name 属性：用于服务器

   option 标签：定义下拉列表中的一个选项（一个条目），value 属性：定义送往服务器的选项值。

   ```html
   <select name="" id="">
     <option value="">男</option>
     <option value="">女</option>
   </select>
   ```

## 示例代码

```html
<!-- 表单容器：form标签 ,action属性向后台提交数据-->
<form action="">
  <!-- label标签：用来描述输入框,for属性：默认是空（对应输入框的id，点击label文本时会自动focus到输入框）-->
  <label for="username">用户名</label>
  <!-- input标签，type属性：text文本输入框、password密码输入框（不可见），submit按钮（默认：提交），button纯按钮，radio单选框,checkbox复选框；placeholder属性显示默认的提示信息 -->
  <input id="username" type="text" placeholder="用户名" />
  <label for="password">密码</label>
  <input id="password" type="password" placeholder="密码" />
  <!-- 单选框,name属性：把两个radio绑定到name，就可以避免两个都选，做到只能选其中一个 -->
  <label>男</label>
  <input name="sex" type="radio" />
  <label>女</label>
  <input name="sex" type="radio" />
  <!-- select下拉框，name属性用于服务器-->
  <select name="" id="">
    <!-- option元素定义下拉列表中的一个选项（一个条目），value属性：定义送往服务器的选项值。 -->
    <option value="">男</option>
    <option value="">女</option>
  </select>
  <!-- 复选框 -->
  <input type="checkbox" />

  <!-- 提交按钮样式，自带提交数据到服务器功能 -->
  <input type="submit" value="登录" />
  <!-- 这只是一个按钮，没有任何功能，需要自己配置 -->
  <input type="button" value="按钮" />
</form>
```

## 作业 2 调查问卷

```html
<h1>问卷调查</h1>
<form action="">
  <label for="username">用户名</label>
  <input id="username" type="text" placeholder="用户名" />
  <br />
  <label for="password">密码</label>
  <input id="password" type="password" placeholder="密码" />
  <br />
  <label>请选择性别</label>
  <br />
  <label>男</label>
  <input name="sex" type="radio" />
  <label>女</label>
  <input name="sex" type="radio" />
  <br />
  <label>最喜欢的运动</label>
  <select>
    <option value="">足球</option>
  </select>
  <br />
  <input type="submit" value="提交" />
</form>
```
