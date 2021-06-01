# 我的blog


## 這是練習 Github Page

## [google](https://www.google.com)

## [test](https://ycchien313.github.io/test/)


# Node.js Crawler 爬蟲
## 步驟
1. 安裝 axios
2. 解析 API
3. 寫 axios 程式

### 1. 安裝 axios
```javascript= 
npm install axios
```
在程式檔案的目錄下安裝 axios，例：

D:\nodejs\crawler.js → D:\nodejs\ 底下安裝 axios


### 2. 解析 API
API：https://www.twse.com.tw/exchangeReport/STOCK_DAY?response=json&date=20210601&stockNo=2330

此為臺灣證券交易所 API，可以看到一個網址帶有三個參數
- url = https://www.twse.com.tw/exchangeReport/STOCK_DAY?
- response = json
- date = 20210601
- stockNo =2330


### 3. 寫 axios 程式
```javascript= 
const axios = require("axios")
const config = {
    method: "get",
    responseType: "json",
    baseURL: "https://www.twse.com.tw/",
    url: "/exchangeReport/STOCK_DAY",
    params: {
        response: "json",
        date: "20210601",
        stockNo: "2330"
    }
};

(function(){
    axios(config)
    .then((response) => {
        console.log(response)       //印出 response object
        console.log(response.data)  //印出 API 提供的資料
    })
})()
```
