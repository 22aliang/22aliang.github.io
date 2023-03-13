---
title: Web 網頁入門初心者 | 學習筆記 
date: 2023-03-13 12:43:57
categories: 初心者筆記系列
tags: HTTP Note 
---
## 前言
  本身是一個非本科的轉職仔，本科是設計科，資質愚鈍，很多東西只看文件需要輔助很多文章才比較能理解。

  因此想透過用自己的文字撰寫來統整目前的知識，再用自己比較熟悉的圖像記憶整理一下，日後讓自己回憶方便。

  若文章中有錯誤也歡迎糾正，感謝大家！

## Web 是如何運作的呢 ? 
  ![img](https://i.imgur.com/eavypn1.jpg)
  + 網頁瀏覽器 → 使用超文本傳輸協定（HyperText Transfer Protocol, HTTP）網頁伺服器（web servers）→ 發送HTTP 請求（request）→ 網頁伺服器→ HTTP 回應（response）


### 靜態網頁
  ![img](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/4895143e-2f54-499c-abbb-33cb9acbd778/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230313%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230313T033804Z&X-Amz-Expires=86400&X-Amz-Signature=70a63afb9d3d107d51c4ff754621bd57141173bc5d5ed118a0303c495e2677e6&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)

### 動態網頁
  ![img](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/ae63c93e-1317-4bfa-baaa-c5a38eab418b/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230313%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230313T033952Z&X-Amz-Expires=86400&X-Amz-Signature=32c67e5e3cf6b15e00a221f13793dc1e0399113b4d4bb9c6fe5492c6c21d6a7e&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)

### 用戶端 Client side
  - 程式語言由HTML、CSS、JaveScript撰寫。 
  - 我們看到的網頁長怎樣

### 伺服器端 Sever-side
  - 常見程式語言PHP、Python、JAVA、C# 與 NodeJS(JavaScript)等...
  - 遞送資訊，優化使用者體驗
  - 購物車庫存管理、歷史紀錄、演算法、會員登入、手遊資料儲存碼、使用者資料分析...

## 什麼是HTTP ?
  - HTTPS( HyperText Transfer Protocol Secure超文本傳輸安全協定 )
  - 利用SSL/TLS來加密封包傳輸
  - 預設port為443

| 推薦服用Will [保哥｜初學者都該學會的 HTTP 通訊協定基礎](https://www.youtube.com/watch?v=Taq5TV1K4XU)

### HTTP請求方式 Http Request Method
  - 當你在網路點擊一個連結、提交一個表單、進行一次搜索等...瀏覽器都會發送一個HTTP給伺服器。
  - `GET` 拿取資料 (應只用在顯示、讀取用途)
  - `POST` 上傳資料，請求伺服器處理 ( 如提交表單、上傳檔案，可能建立、修改現有資源)
  - `PUT` 覆蓋資料(全部)
  - `PATCH` 更新資料(可部分更新)
  - `DELETE` 刪除資料
  - `OPTIONS` 使伺服器回傳該資源支援的所有HTTP請求方法

### HTTP回應 HTTP Response
  - `1xx` ：信息 Informational 接收到request了 需要繼續處理100 Continue：Server 成功接收、但 Client 還要進行一些處理。
  - `2xx`：成功 Successful : 200 0K：請求成功 、201 Created：資源已經被創建，POST、PUT 後可能會收到這樣的回應、204 No Content：成功但沒有回傳的內容（當你發出 Delete 的 request）
  - `3xx`：重定向、轉址 (Redirects)301 Moved Permanently : 請求的網址已經搬家囉
  - `4xx`：用戶端的錯誤 (Client Errors) 可能格式寫錯或漏寫400 Bad Request：請求格式寫錯、資源太大401 Unauthorized：未取得授權、檢視 API 的授權方式、登入等...、403 Forbidden：使用錯誤的驗證404：找不到資源，通常是路徑錯誤，大多是前端的路徑輸入錯誤、422：請求是正確的，可能不符合操作流程（大多可從後端的回應中找到問題）、429：請求次數過多，後端封鎖。
  - `5xx`：伺服器端錯誤 (Server Errors) 伺服器當機、機台燒掉、500 Internal Server Error：伺服器出錯，搶票之類的

  ![img](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/95882cfc-c227-4e7a-ac72-f96dd2242744/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230313%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230313T034444Z&X-Amz-Expires=86400&X-Amz-Signature=1cc230ef9960f23f00ae4329c059e84c3760613cfbb95260a170ff0bc30479c7&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)
  使用google瀏覽器按F12，開啟開發者工具，可在Network中瀏覽，這個網頁下了什麼樣的Request，status欄為Response的狀態，可藉此找出優化網頁速度該從哪裡下手。

## Program, Process, Thread 三者關係
  ![img](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/e3165fc0-e744-4d39-b5e7-c7892f5f93b8/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230313%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230313T034534Z&X-Amz-Expires=86400&X-Amz-Signature=d9bb90c63d8e31b05cf809cea0c9961ab536084c0f7aaab4edfe39b45b7a9c5f&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)
  + 為加深理解，在圖片中加了劇本去理解這之間的關係

  ![img](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/075b3b5a-24fc-4b00-b5ff-ca867c4d07df/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230313%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230313T034620Z&X-Amz-Expires=86400&X-Amz-Signature=347d876ed63fa0f0e7de214dbe74bd02549a94c70e026d2527beea0f2af95b67&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)
  + 也可以打開工作管理員，不同頁籤中相互對照，幫助了解邏輯。

![img](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/a08e92e4-b096-47fa-b42d-1c5848925208/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230313%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20230313T034657Z&X-Amz-Expires=86400&X-Amz-Signature=991f996bf6fbcd2279ddee7453f06712833f1b321058a81a409d37684801bc05&X-Amz-SignedHeaders=host&response-content-disposition=filename%3D%22Untitled.png%22&x-id=GetObject)


## 參考 Reference
[MDN](https://developer.mozilla.org/zh-TW/docs/Learn/Server-side/First_steps/Introduction)

### 學習資料
[六角學院｜前後端都該理解的計算機概論](https://www.youtube.com/watch?v=QuCu4iDpPTU&t=1871s)
[Aaron｜How the Internet Works in 5 Minutes](https://www.youtube.com/watch?v=7_LPdttKXPc) 
[Huli｜從傳紙條輕鬆學習基本網路概念](https://hulitw.medium.com/learning-tcp-ip-http-via-sending-letter-5d3299203660)

### 讀書清單
- 恐龍書 Operation System Concepts
- [RFC 2616](https://www.rfc-editor.org/rfc/rfc2616)