# Always Show Steam Wishlist Rank

一個 UserScript，在 Steam 願望清單的每個項目上顯示擁有者為它設定的排序數字標誌
（例如 `#4`，即官方 API 的 `priority` 值）。

## 行為

- 依名稱／定價／發行日期等排序（網址帶 `?sort=`）時：一律顯示排序標誌。
- 個人排序（自己清單的「您的排序」、別人清單的「個人自訂排序」，網址不帶 `?sort=`）時：
  清單本身已是擁有者的排序，預設**不**顯示標誌。
- 但在個人排序下**使用搜尋框**時：清單被過濾成子集合、排序不再連續，此時會顯示排序
  標誌；**清空搜尋**後即恢復不顯示。

## 安裝

需要 Violentmonkey／Tampermonkey 等 UserScript 管理器。裝好管理器後，開啟
[安裝連結](https://raw.githubusercontent.com/pei-lun/always-show-steam-wishlist-rank/refs/heads/main/always-show-steam-wishlist-rank.user.js)
即會跳出安裝提示。

## 更新

腳本內建 `@updateURL`／`@downloadURL`，指向本專案 GitHub 的 raw 檔案，無需
Greasy Fork 等平台。管理器會定期檢查並在有新版時自動更新（也可在管理器面板手動
觸發「檢查更新」）。
