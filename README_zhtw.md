![GoIndex](themes/logo.png)

GoIndex
====
基於 [Cloudflare Workers](https://workers.cloudflare.com/) 和 [Google Drive](https://www.google.com/drive/) 的功能，你可以部署你的代碼在Cloudflare Workers，實現以目錄形式展示google drive中的文件。

`index.js` 包含 Workers 所需的代碼.

## Demo
material:
[https://index.gd.workers.dev/](https://index.gd.workers.dev/)
classic:
[https://indexc.gd.workers.dev/](https://indexc.gd.workers.dev/)

## 安裝部署方案1
1、在本地安裝 rclone
2、按照 https://rclone.org/drive/ 流程進行授權。
3、執行 rclone config file 查看 rclone.conf 路徑。找到root_folder_id和refresh_token記錄下來。
4、下載 https://github.com/kirbyloco/goindex 中的 index.js  並填入 root 和 refresh_token
5、複製代碼 到 CloudFlare 部署。

## 安裝部署方案2
作者不會記錄refresh_token，但為避免糾紛，建議有條件的同學使用方案1進行部署
1、訪問[https://install.gd.workers.dev/](https://install.gd.workers.dev/)
2、授權認證後，生成部署代碼。
3、複製代碼 到 CloudFlare 部署。

## 文件夾密碼：
在google drive 文件中放置 `.password` 文件來設置密碼。
密碼文件只能保護該文件不被列舉，不能保護該文件夾的子文件夾不被列舉。
也不保護文件夾下文件不被下載。

程序文件中 `root_pass` 只為根目錄密碼，優先於 `.password` 文件


## 更新日誌

1.0.6
添加 classic 模板

1.0.5
添加文件展示頁

1.0.4
修復 注入問題。

1.0.3
修復 `.password` 繞過下載問題。

1.0.2
最佳化前端邏輯
添加文件預覽功能(臨時)
添加前端文件快取功能

1.0.1
添加 README.md 、 HEAD.md 支持

1.0.0
前後端分離，確定基本架構
添加.password 支持
