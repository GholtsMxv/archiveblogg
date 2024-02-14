---
layout: post
title: 超簡單的cf worker代理免費搭建
---

### 前言
大陸地區有**GFW**是人盡皆知的事,翻墻訪問國際互聯網成爲了大陸絕大多數網民獲取國際信息的一道門檻,而其中很多人一聼到翻墻就認爲花錢購買工具才能翻墻,這是錯誤的,翻墻的方法千千萬萬,**免費速度還快**的有cfworker,WARP+,TeamZeroTrust等等,接下來就是利用cfworker進行翻墻的具體**操作過程**

## 1.創建cloudflare賬號

- 進入[cloudflare](https://dash.cloudflare.com/sign-up)注冊賬戶(有賬戶的跳過這一步)

## 2.創建worker  

- 點擊進入側邊欄的Workers & Pages  
- 點擊Create application  
- 再點擊Create Worker  
- 隨便取個名字,最好不要取帶有proxy字樣的名字  
- 再次點擊Deploy  
- 最後點擊Edit code  
- 這樣就完成了worker的創建

## 3.配置worker内容

- 打開[edgetunnel](https://github.com/zizifn/edgetunnel/blob/main/src/worker-vless.js)  
- 複製全選js文件裏的内容  
- 返回你剛才創建的worker編輯界面  
- 刪除默認文件worker.js中的全部文本,將剛才複製的内容粘貼上去  
- 然後回到頂部,找到 `let userID =` 這行代碼,將等號後面單引號裏的内容替換成新的[uuid](https://1024tools.com/uuid),複製到記事本備用  
- 在他的找到 `let proxyIP =` 這行代碼,在後面的引號中添加`103.200.112.108`這串ip地址  
- 最後點擊右上角的Save and deploy


## 4.導入訂閲鏈接

- 等待Save and deploy按鈕變灰,點擊編輯欄右上角的workers.dev  
- 打開後在網址後面添加 /UUID(剛才複製的那個)  
- 等待網頁加載完成,複製以 vless:// 開頭的一整行代碼,導入[代理軟件](https://gholtsmxv.github.io/Application-proxy/)  
- 導入後打開編輯界面,關閉tls,把地址一項改爲[優選ip](https://stock.hostmonit.com/CloudFlareYes),端口改爲80,保存
- 這時候運行代理,打開[Google](https://www.google.com/)測試是否成功.如果失敗,請確保每一步都嚴格按照教程操作.

>### tips
>cfworker代理的具體速度取決於你的**物理位置**和**運營商**,有些特殊的地方注定是用不了的(西藏),還有些地區的運營商也可能會**阻斷**cloudflare的服務,具體使用情況取決於**個人使用環境**.
