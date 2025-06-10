# 農村美食 Cuisine Demo

## 專案簡介 Project Overview
本專案是一個結合政府開放資料的台灣農村美食搜尋網站，提供即時關鍵字搜尋與一鍵導航功能，讓使用者輕鬆探索在地特色美食。  
This project is a Taiwanese rural cuisine search website that integrates government open data, offering real-time keyword search and one-click navigation to help users easily discover local specialties.

## 技術棧 Tech Stack

- HTML5, CSS3 (Grid), jQuery, AJAX  
- 政府開放資料 API (農委會旅遊美食)  
- 響應式設計 (Responsive Web Design)  

## 主要功能 Features

1. **即時關鍵字搜尋 Real-time Keyword Search**  
  
  - 支援 Enter 快捷鍵：在輸入欄按下 Enter 會觸發搜尋。
  - Real-time matching while typing, and Enter key triggers search.

  ```js
  $("#searchInput").keydown(function (e) {
    if (e.key === "Enter") {
      searchDestination();
    }
  });
  ```
  
- 當輸入內容清空時，自動還原所有資料
- When the input field is cleared, the full dataset is automatically displayed again.
```js
  $("#searchInput").on("input", function () {
    let keyword = $(this).val().trim();
    if (keyword === "") {
      showData(allData);
    }
  });
  ```

2. **整合政府開放資料 API Integrated Government Open Data API**  
   - 即時取得最新農村美食資訊。  
   - Fetches latest rural cuisine data from Taiwan’s Council of Agriculture Open Data.
     
3. **一鍵導航至 Google Maps One-click Google Maps Navigation**  
   - 點擊「導航」快速跳轉地圖定位。  
   - Click the "Navigate" button to quickly open Google Maps with the address.

```js
function openMap(address) {
      window.open(
        `https://maps.google.com/?q=${encodeURIComponent(address)}`,
        "_blank"
      );
    }
```

4. **資料完整性檢查 Data Validation**  
   - 過濾缺少圖片或名稱的資料，確保展示內容完整。  
   - Filters out entries missing images or names to ensure content integrity.

5. **響應式設計 Responsive Design**  
   - 適用於桌面與行動裝置，使用 CSS Grid 版面配置。  
   - Supports desktop and mobile devices using CSS Grid layout.

6. **視覺效果 Visual Enhancements**  
   - 雲朵動畫與農村風格設計，提升使用者體驗。  
   - Cloud animations and rural theme design enhance user experience.


## 聯絡 Contact
Tina Lee 
Email: wt.tinalee@gmail.com
