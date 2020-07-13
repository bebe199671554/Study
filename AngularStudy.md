# Angular 學習筆記

@NgModule
>declarations：屬於此 NgModule 的 Component、Directive 與 Pipe 皆放置於此。
>1. **imports**：匯入
>2. **providers**
>3. **exports**：匯出
>4. **entryComponents**：放在這裡的元件通常是用不通過 Route 的方式，而採用動態加入的元件。
>5. **bootstrap**：在此設置的是應用程式通常稱之為 Root Component （根元件） ，而且只有 Root Module 才要設置此屬性。
> *(有設定bootstrap代表其為一個根組件)*
### 元件
>Angular 就會建立、更新、銷燬一些元件。 你的應用可以透過一些可選的生命週期鉤子（比如 ngOnInit()）來在每個特定的時機採取行動。

#  [路由](https://angular.io/guide/router)

[API](https://angular.io/api/router/Route)

[Angular中的組件通訊](https://www.digitalocean.com/community/tutorials/angular-component-communication)

## service
>Service 可以提供給appModule、或任何Component使用，如果要給appModule使用，則需要再src/app/app.module.ts中的@NgModule裡加入

# [依賴注入](https://angular.io/guide/dependency-injection#dependency-injection-in-angular)

[Dependency Injection In Angular 2](https://ithelp.ithome.com.tw/articles/10186702)

### 依賴注入

>依賴注入是一種實現控制反轉的方法，也是一種軟體設計模式。在這種模式下，一個或更多的依賴(或服務)被注入(或透過參考傳遞)到一個獨立的物件(或用戶端)中，然後成為該用戶端狀態的一部分。


### Angular 的依賴注入有三個重要的概念：
1. **Injector (注入器)**- 會被實例依賴的注入對象。
2. **Provider (提供者)** - 告訴 Injector 如何創建一個依賴實例的架構譜。
3. **Dependence (依賴)**- 創建對象的 Type

## Injector注入器
*參考Angular 高速聰明該發多介面*
>Injector 的主要作用是把注入的服務標記為可注入的狀態，當然@Injectable 這個裝飾器是非必須項目，只有在一個服務依賴於其他服務時才必須使用到@Injectable。例如我們有兩個服務，

@Injectable()是angular的service使用做依賴注入的裝飾詞，可以使Service成為可被注入的元件。

## [@Inject() 和 @Injectable之間的區別](https://medium.com/@dipakkolhe/difference-between-inject-and-injectable-ac15873de7a4)

**@Inject()**

**Inject 機制必須要注入一個建構子**

```ts
 @Injectable()
export class SomeService {
constructor(@Inject(Http) private http:Http, @Inject('sometoken') obj) {
}
}
```
```ts
import { Component } from '@angular/core';
import { ChatWidget } from '../components/chat-widget';

@Component({
  selector: 'app',
  template: `Encryption: {{ encryption }}`
})
export class App {
  encryption = this.chatWidget.chatSocket.encryption;

  constructor(private chatWidget: ChatWidget) { }
}
```

**@Injectable**

**Injectable 則是可以作為依賴(Dependence)注入**

```ts
@Injectable()
export class SomeService {
constructor(private http:Http) {
}
}
```
```ts
import { Injectable } from '@angular/core';
import { AuthService } from './auth-service';
import { AuthWidget } from './auth-widget';
import { ChatSocket } from './chat-socket';

@Injectable()
export class ChatWidget {
  constructor(
    public authService: AuthService,
    public authWidget: AuthWidget,
    public chatSocket: ChatSocket) { }
}
```


## safe navigation operator ( ?. )
>為了防止出現null reference exception，我們可以使用?.，當值為空值時，會直接傳回空白，可以避免產生不必要的exception

# 生命週期
Lifecycle Hooks

Lifecycle sequence

* **ngOnChanges()**
    
    Angular設置數據綁定的輸入屬性。會在ngOnInit()之前被呼叫

* **ngOnInit()**
    
    在Angular之後初始化指令，組件首先顯示數據綁定屬性，並設置directive及component的輸入屬性。

* **ngDoCheck()**

    檢測Angular無法或無法自行檢測到的更改，並採取相應措施。

* **ngAfterContentInit()**

    在Angular將外部內容設置到template之後被呼叫。  

* **ngAfterContentChecked()**

    在Angular檢查投影到組件中的內容之後被呼叫。

* **ngAfterViewInit()**
    
    初始化組件的template和sub-template之後被呼叫。

* **ngAfterViewChecked()**

    在Angular檢查組件的視圖和子視圖之後作出響應。

* **ngOnDestroy**

    在Angular破壞指令/組件之前進行清理。取消訂閱Observables和事件處理程序以避免內存洩漏。

# [表單內容](https://angular.tw/guide/reactive-forms)
### 使用formbuilder的 好處
- Component 和 Template 構建表單
- 雙向綁定 [(ngModel)] 讀寫表單表。
- ngControl追蹤表單狀態和有效性。
- 根據ngControl改變 CSS。
- 顯示驗證錯誤消息並啟用/禁止表單。
- 使用本地模板變量共享控制間的信息。

## [響應式表單](https://angular.tw/guide/reactive-forms)

>如果要使用響應式表單，就要從 @angular/forms 包中匯入 ReactiveFormsModule 。

formbuilder 提供表單處理

1. 匯入FormBuilder類

    ```import { FormGroup, FormControl, FormBuilder } from '@angular/forms';```

2. 注入FormBuilder服務
    >FormBuilder 是一個可注入的服務提供商，它是由 ReactiveFormModule 提供的。

    ```constructor(private fb: FormBuilder) { }```

3. 產生表單控制元件
    >FormBuilder 服務有三個方法：
    - control ( )
    - group ( )
    - array ( )

    FormBuilder 提供了一個語法糖，以簡化 FormControl、FormGroup 或 FormArray 實例的建立過程。 它會減少建構複雜表單時所需的樣板程式碼的數量。


required 可以要求使用者必須輸入該項

- 步驟(TS)
    1. 新建一個FromGroup 物件
    2. 建構實例
    3. 使用FromBuild 來製作表格
        - 定義表格的預設值
    4. 提交執行的function

# Directive

## Attribute Directives(屬性型)
Directive有分為結構型跟屬性型的

而Angular有三中directive：
* 元件-包含template的directive。
* 結構指令-通過添加和刪除DOM元素來更改DOM布局。(e.g. ngFor、ngIf)
* 屬性指令-改變元素，組件或其他指令的外觀行為(e.g. ngStyle)

## Structural Directives(結構型)



# [串接後端API](https://medium.com/@maiccaejfeng/angular-9-%E7%B3%BB%E5%88%97-3-%E5%A6%82%E4%BD%95%E4%B8%B2%E6%8E%A5%E5%BE%8C%E7%AB%AF-api-ed40d3c0b8bc)

1. 匯入HttpClinetModule(app.module.ts)
2. 注入HttpClient到component中(.component.ts)
3. 透過HTTP POST 串接後端API(.component.ts)
4. 把res 資料整理成前端想要的樣子(.component.ts)
5. 在html檔串接資料(component.ts)


# switchMap
https://www.learnrxjs.io/learn-rxjs/operators/transformation/switchmap


*MATTABLEDATASOURCE*
*this.dataSource.data*

-----
表單更新方式
setValue、patchValue、reset

- **patchValue**
把表單的值給更新
- **setValue**
跟 patchValue 有一點不一樣，當我們提供一個 FromGroup 中並不存在的欄位時，會出現一個錯誤。除此之外，與 patchValue 並無不同。
- **reset**
正常情況下，表單需要提供一個重置按鈕時呼叫此方法。
-----
https://lawrencetech.blogspot.com/2017/06/angular_3.html


## resolve
------
resolve保證了資料獲取後再進行路由跳轉，防止因為資料延遲而出現短暫的空元件情況，以此增強使用者體驗。

應用resolve還可以進行路由攔截，例如某些網站如果使用者未登入，在跳轉到某一頁面時會提示未登入然後強行回跳至前一頁面，這時如果使用resolve就可以在跳轉發生前判斷登入狀態以決定是否允許跳轉。

https://angular.io/guide/router#resolve-pre-fetching-component-data


先建一個service
在