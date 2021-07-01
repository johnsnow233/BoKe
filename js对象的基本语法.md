## 声明对象的两种语法
```javascript
    let obj = {'name': 'john', 'age':18}（更简单）
    let obj = new Object ({'name':'john'})（更规范）
    console.log({'name': 'john', 'age':18})
```
## 如何删除对象的属性

* 使用delete
```javascript
delete obj.xxx 或者 delete obj.['xxx']
```
* 不含属性名
```javascript
'xxx' in obj===false
```
* 含有属性名但是值为undefined
```javascript
'xxx' in obj&&obj.xxx===undefined
```
* 注意obj.xxx===undefined
```javascript
不能判定'xxx'是否为obj的属性,但是值可以是undefined.
```
## 查看所有属性

* 查看自身属性
```javascript
Object.keys(obj)
```
* 查看自身属性和共有属性
```javascript
console.dir(obj)
```
* 判断一个属性是自身的还是共有的
```javascript
Object.hasOwnProperty('toString')// 共有的返回false,自身的返回true
```
* 查看具体属性
```javascript
obj['key'];//推荐
obj.key;
```
## 修改或增加属性
* 直接赋值
```javascript 
 let obj = {name:'john'}//name是字符串
obj.name = 'john'//name是字符串
obj['name']='john'
obj[name]='john'//错因为name的值不确定
obj['na'+'me']='john'
let key = 'name';obj[key] = 'john'
let key = 'name';obj.key = 'john'//错，因为obj.key等价于obj['key']
```
* 批量赋值
```javascript
Object.assign(obj,{age:18,gender:'femal'})
```
* 修改或增加共有属性
```javascript
let obj = {},obj2 ={}//共有toString
//obj.toString = 'xxx'只会修改自身属性
//obj2,toString还是在原型上
//一般不要修改原型会产生问题，如果偏要修改
Object.prototype.toString='xxx'
```
* 修改隐藏属性
```javascript 
let obj = Object.create(common)//以common为原型创建obj

obj.name = 'ben'

规范如果要改就一开始改，不要后来再改
```
## 'name' in obj和obj.hasOwnProperty('name') 的区别

```javascript 
function Person (){ 
       }
      Person.prototype.name = "原型的名字";
       var p1  = new Person();
       
       //使用in判断对象中是否由属性时，若自身没有，在原型中找到也是返回true
       console.log("name" in p1);

       //使用hasOwnproperty()判断对象是否含有属性时，只有自身有才返回true
       console.log(p1.hasOwnProperty("name"));

```