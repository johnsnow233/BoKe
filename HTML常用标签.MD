# a标签的常用用法

* 属性
  

1. href
   
```html
<a href='www.baidu.com'>百度一下</a>
```
   2. target
   ```html
<a href='www.baidu.com' target='_blank'>百度一下</a> <!-- 在新窗口打开一个新的页面-->

<a href='www.baidu.com' target='_self'>百度一下</a> <!-- 在当前窗口打开页面，默认值-->
<a href='www.baidu.com' target='_parent'>百度一下</a> <!-- 在上一级窗口打开，通常用于从父串口打开子窗口，或者<iframe>里面的链接-->
<a href='www.baidu.com' target='_top'>百度一下</a> <!-- 在最顶层窗口打开链接-->
```
  上面代码点击后，浏览器会新建一个窗口，在该窗口打开链接，并且新窗口没有名字。

注意，使用target属性的时候，最好跟rel="noreferrer"一起使用，这样可以避免安全风险。

  3. download
   ```html
   <a href='test.html' dowmload='文件名'>下载</a>
   ```
上面代码点击后，会出现下载对话框。

注意，download属性只在链接与网址同源时，才会生效。也就是说，链接应该与网址属于同一个网站。

如果download属性设置了值，那么这个值就是下载的文件名。

  4. rel=noopener

* 作用
  
  1. 跳转外部页面
  2. 跳转内部锚点
  3. 跳转到邮箱或电话
   
* a的href的取值
  
  1. 网址

     https://google.com

     http://google.com

     //google.com

   2. 路径
   
      /a/b/c以及a/b/c

      index.html 以及./index.html

  3. 伪协议
   
      javascript:代码;
    ```html
    <a javascript:alert(1);>查看</a><!-- 优点： 不会刷新页面你，不会改变页面位置。-->
    ```
     
     mailto:邮箱
     ```html
       <a mailto:alert(1)>联系我们</a>
     ```
     
     tel:手机号

     ```html
     <a tel=1212212122>手机号</a>
     ```
  4. id
```html
     <a href ='#xxx'> </a> 
```
注意: 可以使用 href="#top" 或者 href="#" 链接返回到页面顶部

# img 标签的用法

* 作用
  
  发出get请求展示一张图片

* 属性
  
  alt/height/width/src

```html
<img src="image.jpg" width="300" height="500" alt="这是一张图片" title="图片名字"> <!-- src属性可以接受本地图片路径也可以接受网络图片路径；width可以设置图片宽度；height可以设置图片高度；alt可以在图片无法正常率显示下做出对图片的相应的提示，如果图片可以正常显示则无法显示文字提示，提高用户体验度；title为图片加上悬浮框提示-->
```
* 事件
  
  onload/onerror

  ```html
       <img  id='xxx' src="错误的图片.jpg" alt="测试">
    <script>
        xxx.onload=function(){
            console.log('图片加载成功')
        }
        xxx.onerror=function(){
            console.log('图片加载失败')
            xxx.src='./404.jpg'
        }
    </script> 
    <!--给错误的图片重定向并展示404图片 -->
  ```
* 响应式
  
  max-width:100%
  * 作用：该CSS样式可以使图片自适应各种机型
* 可替换元素
  
  待更新
# table 标签的用法

* 相关标签
  
  table

  thead 

  tbody  

  tfoot

  tr  表格的一行

  td  表格数据

  th  表格‘标题’

  ```html
       <table>
        <thead> 
            <tr>
                <th></th>
                <th>小明</th>
                <th>小虎</th>
                <th>小伟</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th>数学</th>
                <td>89</td>
                <td>88</td>
                <td>100</td>
            </tr>
            <tr>
                <th>语文</th>
                <td>99</td>
                <td>88</td>
                <td>100</td>
            </tr>
        </tbody>
        <tfoot>
            <th>总分</th>
            <td>187</td>
            <td>176</td>
            <td>200</td>
        </tfoot>

    </table>
  ```


* 相关样式
  
  table-layout
  border-collapse
  border-spacing

```css
table, th, td{
    /* 设置边框 */
    border: 1px solid blue; 
    /* 表格自动布局,其中属性fixed为固定布局 */
    table-layout: auto; 
    /* 相邻边被合并 */
    border-collapse: collapse;
    /* 相邻单元格之间的距离 */
    border-spacing: 0ch;
}
```

# 其他感想

1. form标签

* 作用
  
    发get或post请求，然后刷新界面

* 属性
* 
   action/autocomplete/method/target

* 事件

   onsubmit

1. input标签
   
 * 作用
  
  让用户输入内容

  * 属性
  
   类型
   

   其他


* 事件
  
  onchange/onfocus/onblur

* 验证器
  
  html5 新增功能
  
  