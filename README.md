# cuisine Demo

🌟 Highlights

## 1. 即時關鍵字搜尋 搜尋欄功能
  
  - 支援即時搜尋：輸入文字時，自動比對關鍵字。
  - 支援 Enter 快捷鍵：在輸入欄按下 Enter 會觸發搜尋。
  - 清空輸入欄時，自動顯示全部資料。

  // 當使用者在搜尋欄按 Enter 執行搜尋
  ```js
  $("#searchInput").keydown(function (e) {
    if (e.key === "Enter") {
      searchDestination();
    }
  });
  ```
  
  // 當輸入內容清空時，自動還原所有資料
```js
  $("#searchInput").on("input", function () {
    let keyword = $(this).val().trim();
    if (keyword === "") {
      showData(allData);
    }
  });
  ```

2. 整合政府開放資料 API
   - 串接 農委會旅遊美食 Open Data，即時取得最新的農村美食資訊。

3. 一鍵導航至 Google Maps
   - 點擊「導航」按鈕即可跳轉 Google Maps，快速查找地點位置與路線。

```js```
function openMap(address) {
      window.open(
        `https://maps.google.com/?q=${encodeURIComponent(address)}`,
        "_blank"
      );
    }
````````

4. 資料完整性檢查
   - 過濾資料中缺少圖片或名稱的不完整項目，提升使用者體驗。

```js```
//jQuery
for (let i = 0; i < data.length; i++) {
        if (!data[i] || !data[i].PicURL || !data[i].Name) {
          console.log("Skipping entry", i);
          continue;
        }
````````````````

5. RWD 響應式設計
  - 利用純 CSS 和 Grid 版面配置，打造手機與桌機裝置皆適用的響應式介面，提升跨裝置的使用體驗與瀏覽舒適度。

6. 趣味視覺元素
   - 使用雲朵動畫與鄉村意象設計風格，營造農村氣息。
