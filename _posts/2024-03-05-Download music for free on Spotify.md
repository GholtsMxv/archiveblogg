---
layout: post
title: 利用SpotDL下載Spotify音乐
---

## ※[SpotDL項目地址](https://github.com/spotDL/spotify-downloader/tree/master)
  
## 1.安裝Python環境

- 進入[Python](https://www.python.org/downloads/)官網下載安裝包
- 按照提示進行安裝
- 在安裝過程中勾選配置環境變量

## 2.安裝SpotDL

- 新建一個AdministratorCMD窗口任務
- 依次執行代碼 ```pip install spotdl``` ```spotdl --download-ffmpeg```

## 3.Enjoy

- 輸入代碼 ```spotdl``` ```spotdl download [spotify單曲鏈接]``` 或者 ```spotdl download [spotify歌單鏈接]``` 即可下載
- 默認下載地址在 ```C:\Users\[你的Windows賬戶名]```

## 4.Advanced

- 默認配置文件在 ```C:\Users\[你的Windows賬戶名]\.spotdl\config.json```
  
- ```output``` 是配置默認下載地址
  
- ```format``` 是配置下載音頻格式,例如 MP3,M4A 和 OPUS
  
- 若要啟動 Web UI，請執行 ```spotdl web``` ,同時修改配置文件中 ```web_use_output_dir``` 項為true
  
- 更多詳細配置可以參考[SpotDL官方文檔](https://github.com/spotDL/spotify-downloader/blob/master/docs/usage.md)

>SpotDL 使用 YouTube 作為音樂下載來源, 此方法用於避免與從 Spotify 下載音樂相關的任何問題  
>使用者應對自己的行為和潛在的法律後果負責。 SpotDL不支援未經授權下載受版權保護的資料，並且對使用者行為不承擔任何責任
