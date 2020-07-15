# Microsoft Azure Fundamentals
AZ-900
(及格分700)

單元一，雲端概念
公有 私有
混和運算
基礎結構及服務，服務及平台，軟體及服務

- 高可用性
- 延展性
    - 擴展資源時，會需要升級相對應的硬體
    - 針對求縮放
- 彈性
    - 可調整規模
    - 可大可小
    - 雲端空間的優勢
- 容錯能力
    - 微軟責任
1. 嚴重損壞修復(備份目標)
2. VM開設(第二單元提及)
4. 預測成本
5. 安全性
   - 分散式聚集服務
   - DDoS保護
6. 

### 規模經濟

### 公有雲服務
沒有成本支出只有營運支出
### 私有雲服務
完全掌控，必須自己負責
### 混和雲服務
合規性

- laaS
    - 結構即服務
- PaaS
    -平台即服務
- SaaS
    - 隨用即付
----
什麼是 Shared Responsibility Model?

當您考慮並評估公用雲端服務時，請務必瞭解共用責任模型，以及由雲端提供者處理哪些安全性工作，以及由您處理哪些工作。更多資訊請參考: https://docs.microsoft.com/zh-tw/azure/security/fundamentals/shared-responsibility

----
Azure 目前在多少個地區建置資料中心呢?

目前超過 60 個地區，可在 140 個國家/地區使用。詳細資訊請參考: https://azure.microsoft.com/zh-tw/global-infrastructure/regions/

----
Azure 的虛擬機器、App Service 和 Microsoft 365，分別是哪種類型的服務呢?

虛擬機器是 IaaS App Service 是 PaaS Microsoft 365 是 SaaS

----
Pizza as a Service?!

影片中引用了生活化的例子，幫助你進一步了解與分辨什麼是 IaaS/PaaS/SaaS，真的十分有趣。更多的資訊請參考: https://www.episerver.com/articles/pizza-as-a-service

----

單元二，核心服務

討論如何建置中心
核心軟體
管理工具

可用性

可集性
資源群組
備份

管理群組概念

訂閱是你建立資源的地方

- 租用戶

- 訂閱

PaaS


- 租用戶

- 訂閱

/24=255.255.255.0

1. 站到點
2. 點到點
3. 點對站
4. 站對站

1. 結構性資料
2. 半結構性資料
3. 非結構性資料


---
詳解 Availability Zone

可用性區域是高可用性供應專案，可保護您的應用程式和資料不受資料中心失敗的影響。 詳細資訊請參考官方文件說明: https://docs.microsoft.com/zh-tw/azure/availability-zones/az-overview#availability-zones

---
如何安裝 Azure CLI?

Azure CLI 可以在 Windows、macOS 和 Linux 環境中安裝。 也可以在 Docker 容器和 Azure Cloud Shell 中執行。 安裝步驟請參考官方文件: https://docs.microsoft.com/zh-tw/cli/azure/install-azure-cli?view=azure-cli-latest

----



單元三，
儲存體帳戶

邏輯應用
>對輸入資料做決定時需要一個邏輯應用

路由服務
>


---
常見的 Resource Group 使用方式 有哪些?

Resource Group 方便企業針對各種需求將 Azure 服務進行分類，分類的目的就是方便管理這些服務。 如果你想要在 Azure 平台部署一套 EIP 網頁應用程式，這程式包含前端的網站網頁、中間的邏輯處理程式、以及後端的資料庫等，你就可以把這些放在相同的 Resource Group。 又或者，如果你建構的是對外營運且流量龐大的線上遊戲或電子商務平台，你可以將前端數量龐大的網頁伺服器放在相同的 Resource Group，再將後端的 MS-SQL 資料庫放在另外一個 Resource Group。 更多的 Resource Group 概念與運用方式，請參考官方文件: https://docs.microsoft.com/zh-tw/azure/azure-resource-manager/management/overview

---


單元四，價格及運算
Azure核心服務

