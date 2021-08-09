## 表格的基本操作

**row，行**,**column，列**

1. talbe 标签：表格容器
   border 属性: 表格样式
2. tr 标签：一行

3. td 标签：一行的单元格

   colspan 属性: 横向合并单元格

   ```html
   <!-- 3是3个格, 3列 -->
   <td colspan="3">学生列表</td>
   ```

   rowspan 属性：纵向合并单元格

   ```html
   <!-- 3是3个格，3行 -->
   <td rowspan="3">1班</td>
   ```

## 示例代码

```html
<table border="1">
  <tr>
    <!-- colspan用来横向合并单元格，3是3个格 -->
    <td colspan="3">学生列表</td>
  </tr>
  <!-- row 一行用tr -->
  <tr>
    <!-- 一行的单元格 -->
    <td>1</td>
    <td>小红</td>
    <td>2</td>
  </tr>
  <tr>
    <!-- 一行的单元格 -->
    <td>2</td>
    <td>小亮</td>
    <td>4</td>
  </tr>
  <tr>
    <!-- 一行的单元格 -->
    <td>3</td>
    <td>小明</td>
    <td>5</td>
  </tr>
</table>
```

```html
<table border="1">
  <!-- row 一行用tr -->
  <tr>
    <!-- colspan 用来横向合并单元格，3是3个格 3列 -->
    <td colspan="4">学生列表</td>
  </tr>
  <tr>
    <!-- 一行的单元格 -->
    <!-- rowspan用来纵向合并单元格，3是3个格，3行 -->
    <td rowspan="3">1班</td>
    <td>1</td>
    <td>小红</td>
    <td>2</td>
  </tr>
  <tr>
    <!-- 一行的单元格 -->
    <td>2</td>
    <td>小亮</td>
    <td>4</td>
  </tr>
  <tr>
    <!-- 一行的单元格 -->
    <td>3</td>
    <td>小明</td>
    <td>5</td>
  </tr>
</table>
```

## 作业 1 显示学生信息的表格

```html
<table>
  <thead>
    <th>班级</th>
    <th>序号</th>
    <th>姓名</th>
    <th>性别</th>
    <th>成绩</th>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2">1班</td>
      <td>1</td>
      <td>小米</td>
      <td>男</td>
      <td>0</td>
    </tr>
    <tr>
      <td>2</td>
      <td>小志</td>
      <td>男</td>
      <td>100</td>
    </tr>
    <tr>
      <td rowspan="3">2班</td>
      <td>3</td>
      <td>小明</td>
      <td>男</td>
      <td>80</td>
    </tr>
    <tr>
      <td>4</td>
      <td>小红</td>
      <td>女</td>
      <td>70</td>
    </tr>
    <tr>
      <td>5</td>
      <td>小吕</td>
      <td>男</td>
      <td>100</td>
    </tr>
  </tbody>
</table>
```
