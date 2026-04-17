# 🍃 臺中親子樂活指南 | Taichung LOHAS Park Guide

> 在城市綠洲中，品味質感育兒生活。為現代風格家庭打造的臺中綠意指南，輕鬆探索每一處讓孩子放電、讓父母放鬆的自然角落。
> 
> *Savor quality parenting life in the urban oasis. A green guide tailored for modern families to easily explore nature corners in Taichung where kids can burn off energy and parents can relax.*

![App Screenshot](https://via.placeholder.com/1000x500.png?text=Placeholder:+Add+a+screenshot+of+your+beautiful+mobile+and+desktop+UI+here)

---

## 📱 給家長的使用指南 | Quick Guide for Parents (No Coding Required!)

這款網頁應用程式專為忙碌的家長設計，無需下載佔空間的 App，只需兩個步驟，就能將它加入手機桌面，隨時隨地像一般 App 一樣使用！
*This web app is designed for busy parents. No need to download a heavy app from the store. With two simple steps, you can save it to your phone's home screen and use it anytime!*

### 如何安裝到手機桌面？ | How to add to your Home Screen?
1. **打開網頁 (Open the link):** 在手機瀏覽器 (Safari 或 Chrome) 中打開本網站的專屬網址。 *(Open the live website link in your mobile browser).*
2. **加入主畫面 (Add to Home Screen):**
   * **🍎 Apple iOS (Safari):** 點擊螢幕底部的「分享」圖示 (正方形加上箭頭) ➔ 選擇「加入主畫面」。 *(Tap the "Share" icon at the bottom ➔ Select "Add to Home Screen")*.
   * **🤖 Android (Chrome):** 點擊螢幕右上角的「選單」圖示 (三個點) ➔ 選擇「加到主畫面」。 *(Tap the 3-dot menu at the top right ➔ Select "Add to Home Screen")*.
3. **完成！(Done!):** 手機桌面上會出現一個專屬圖示，下次要找公園，點開就能秒速查詢！ *(A shortcut will appear on your screen. Tap it anytime to instantly search for parks!)*

---

## 💻 技術亮點 | Technical Highlights

This project transforms a dense, rigid open-data JSON spreadsheet into a premium, consumer-facing application. It showcases a deep focus on both **Frontend UI/UX** and **Algorithmic Data Filtering**.


### 🎨 UI/UX 體驗升級 (UI/UX Enhancements)
* **北歐風質感設計 (Scandinavian Design System):** 捨棄傳統政府資料庫的生硬外觀，採用低彩度鼠尾草綠、溫暖米白與圓角設計，打造符合現代父母審美的視覺體驗。 *(Replaced rigid database aesthetics with a warm, modern Scandinavian color palette tailored for a premium user experience).*
* **響應式手機卡片設計 (Mobile-First Responsive Cards):** 透過 CSS Media Queries，在手機端自動將傳統的橫向資料表轉換為獨立的「公園資訊卡」，解決手機用戶需要不斷左右滑動的痛點。 *(Transforms horizontal data tables into clean, readable individual Park Cards on mobile devices).*
* **視覺化設施標籤 (Amenity Badges):** 採用資料壓縮 (Data Compression) 概念，將 8 個獨立的設施欄位合併，並轉化為帶有 Emoji 的彩色藥丸標籤 (Pill Badges)，讓使用者一目了然。 *(Condenses 8 sparse data columns into colorful, instantly readable visual tags).*

### 🔍 智慧搜尋功能 (Advanced Search Functionality)
* **雙重比對搜尋邏輯 (Dual-Check Search Logic):** 突破傳統僅能搜尋「儲存格數值」的限制。當使用者輸入「沙坑」(Sandbox)，系統不僅會比對儲存格內容，還會智慧反查「欄位名稱」(Column Headers)，確保只要該公園有該設施，就絕對不會漏搜。 *(A custom search algorithm that maps user keywords against both cell values AND column headers to guarantee accurate facility matching).*
* **懸浮選單與分頁系統 (Sticky Filters & Pagination):** 搜尋列與下拉選單具備毛玻璃懸浮效果 (Frosted glass sticky header)，無論往下滑多深都能隨時調整條件。搭配動態分頁系統 (Dynamic Pagination)，確保畫面載入順暢不卡頓。 *(Ensures filters are always accessible while scrolling, paired with JS-driven pagination to keep the DOM lightweight).*
* **智慧防呆空白狀態 (Smart Empty State):** 當找不到符合條件的公園時，提供優雅的提示畫面與「一鍵清除條件」按鈕，避免使用者陷入操作死胡同。 *(Prevents user dead-ends with a friendly empty state illustration and a 1-click filter reset button).*

---

## 🛠️ 開發者設定指南 | Developer Local Setup

Because this application uses the Javascript `fetch()` API to load the `111TCpark.JSON` file, simply double-clicking the `index.html` file will result in a CORS error on modern browsers. You must run it through a local web server.

**Step 1:** Clone the repository.
```bash
git clone [https://github.com/yourusername/taichung-parks.git](https://github.com/yourusername/taichung-parks.git)

**Step 2:** Open the folder in VS Code.

**Step 3:** Use the Live Server extension (or any local server like Python's http.server) to launch index.html.

Bash
# Python 3 alternative
python -m http.server 5500

<FollowUp label="Want to add interactive Google Maps links?" query="How can we upgrade the dat

