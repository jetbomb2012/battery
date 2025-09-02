# 鋰電大聯盟購物系統合約（contract.md）

本合約文件定義 battery.party 購物系統的模組架構、部署規範、資料安全條款與 OSC 模組導入方式。所有模組部署、擴充、驗證、與使用者互動皆須符合本文件所列條件。

---

## 一、系統架構

- **主域名**：[`https://battery.party`](https://battery.party)
- **購物模組入口**：[`https://battery.party/catalog/index.php`](https://battery.party/catalog/index.php)
- **管理模組入口**：[`https://battery.party/admin/index.php`](https://battery.party/admin/index.php)
- **模組核心**：Open Source Commerce (OSC) v2.2
- **部署路徑**：
  - `/var/www/battery.party/catalog/`
  - `/var/www/battery.party/admin/`

---

## 二、模組導入規範

### 2.1 OSC 模組配置

- 所有 OSC 模組已部署至 Apache 虛擬主機，並啟用 PHP 解析。
- `configure.php` 設定檔已正確設置資料庫連線參數，並設為 `apache:apache` 權限。
- 模組已通過指令測試，確認可解析常數並正常載入。

### 2.2 購物流程

- 顧客可透過 [`/catalog/index.php`](https://battery.party/catalog/index.php) 進入商品瀏覽與購物流程。
- 結帳模組 `/catalog/checkout.php` 已啟用 SSL 加密，保障交易安全。
- 管理員可透過 [`/admin/index.php`](https://battery.party/admin/index.php) 登入後台，進行商品、訂單、顧客管理。

---

## 三、資料安全與驗證

- 所有模組部署前均經由 Jet-Bomb 指令驗證，包含：
  - 檔案完整性確認
  - 權限修正
  - Apache/PHP 模組啟動狀態
- 系統已啟用 HTTPS，並部署有效 SSL 憑證。
- 所有資料庫連線均使用加密通道，並限制外部存取。

---

## 四、模組維護與擴充

- 所有模組版本控管採用 GitHub Pages 與 assets.zip 備份機制。
- 未來可擴充 Shopee 教學模組、AI anchor 渲染模組，並掛載至 `/edu/` 或 `/ai/` 子路徑。
- 所有擴充模組須通過 Jet-Bomb 指令驗證流程，方可部署。

---

## 五、違約條款與撤除機制

- 任何未經授權之模組導入、路徑漂移、設定錯誤、或違反本合約條款者，將立即撤除並記錄違約紀錄。
- 所有部署行為皆視為已閱讀並接受本合約條款。

---

**部署完成時間**：2025-09-03  
**部署者識別**：Jet-Bomb Tactical Executor  