---
layout: post
title: 利用YT-DLP下載幾乎任何影片
---

## ※[YT-DLP項目地址](https://github.com/yt-dlp/yt-dlp) ##

## 1.安裝Python環境

- 進入[Python](https://www.python.org/downloads/)官網下載安裝包
- 按照提示進行安裝
- 在安裝過程中勾選配置環境變量

## 2.安裝ffmpeg

- 進入[ffmpeg](https://www.ffmpeg.org)官網下載安裝包
- 按照提示進行安裝
- 手動添加環境變量
 - 1.打開“計算機”->“内容(屬性)”->“進階系統設置”->“環境變量”
 - 2.在系統變量部分找到“Path”，點擊“編輯”
 - 3.在“變量值”中添加 ffmpeg.exe 所在的文件夾路徑
 - 4.点击确定，完成环境变量配置

## 3.安裝yt-dlp

- 新建一個AdministratorCMD窗口任務
- 執行代碼`pip install yt-dlp`

## 4.Enjoy

- 輸入`yt-dlp` `yt-dlp [影片鏈接]`即可下載
- 輸入`yt-dlp -f ‘bv[ext=mp4]+ba[ext=m4a]’ –embed-metadata –merge-output-format mp4 [影片鏈接]`即可下載最佳mp4影片+最佳m4a音頻格式並合成mp4

## 5.Advanced

- yt-dlp支持解析下載該[列表](https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md)内的視頻鏈接
- 如需指定下載地址,可以使用`-o`或`--output`參數,例如`yt-dlp [影片鏈接] -o "F:/%(title)s.mp4"`
- 更多詳細配置可以參考[YT-DLP官方文檔](https://github.com/yt-dlp/yt-dlp?tab=readme-ov-file#usage-and-options)
