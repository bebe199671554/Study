# 深入了解 TypeScript
`選擇 TypeScript的 理由`
* 增加類類型
* 兼容當前及未來JS特性

1. TS的類型系統
 * 有利於程式碼重構
 * 提供類型型別

***
>### Interfaces：
>TS有一種宣告方式通常稱為Duck typing(鴨子類型) 或是 structural subtyping(結構化型別系統)，或是統稱interface

```Ts
//用法
interface labelValue{
    label:string
}
//如果要定義不一定會存在的參數(非必填)
interface labelValue{
    label?:string
}
//唯獨
interface labelValue{
    readonly label?:string
}
```
>TIP：也可以定義一個唯獨的陣列
```Ts
let a:number[]=[1,2,3,4]
let ro:ReadonlyArray<number>=a
ro[0]=12 //Error
ro.push(8)//Error
ro.length=100//Error
a=ro; //Error
```
> **readonly vs const** : *const* 只是禁止物件被複寫，而
> *readonly* 則是設定物件中的參數不會被複寫
```ts
編譯器執行過度屬性檢查
interface SquareConfig{
    color?: string
    width?: unmber
}
function createSquare(config:SquareConfig):{color:string, area:number}{
    //...
}
let mySquare = createSquare({colour: 'red',width:100})
// error: Object literal may only specify known properties, but 'colour' does not exist in type 'SquareConfig'. Did you mean to write 'color'?

interface SquareConfig{
    color?: string 
    width?: number
    [propName: string]:any
}
//[propName: string]: any;
//這句話的意思是說我設定屬性質是any，
//而因為屬行名稱一定是string，所以前半段的propName就設定其形態是string
//後半段因為不知道使用者會傳入什麼樣的型態資料，故使用any來撰寫

//另外還有一種方法 你直接宣告一個 SquareOptions 物件來放入 createSquare 中也不會有錯誤出現

let squareOptions = { colour: "red", width: 100 }
let mySquare = createSquare(squareOptions)
```
### Function Types

interfaces 描述一個 function type 的時候只需要定義 Parameter列表和回傳值

每一個 parameter都需要明確的定義名稱和類別
```
interface SearchFunc{
(
    
)
}
```
***
 
truthy

在JS中，有許多數值，在邏輯判斷中，其結果與```false```等價。由於其數值實際並非```false```，因此，特別稱此數值為**falsy value**




foreach 

- in
```
for (變數 in 物件) {...
}

var o = {a:1, b:2, c:3};

function show_props(obj, objName) {
  var result = "";
    
  for (var prop in obj) {
    result += objName + "." + prop + " = " + obj[prop] + "\n";
  }
    
  return result;
}

alert(show_props(o, "o")); /* alerts (in different lines): o.a = 1 o.b = 2 o.c = 3 */ 

```
- of
```
const array1 = ['a', 'b', 'c'];

for (const element of array1) {
  console.log(element);
}

// expected output: "a"
// expected output: "b"
// expected output: "c"


```


boolean||
null??