# 文字搜尋系統
## Proposal Report

### 動機與目標
<!-- 說明為什麼想做這個專題 -->
動機：傳統搜尋方式，像是瀏覽器內建搜尋：Ctrl + F，雖然可以快速在單一頁面中搜尋文字，但在面對複雜查詢條件或不完整輸入時，能力有限。此外，當資料量增加或查詢次數提高時，若使用 List 作為資料結構，查詢效率也可能下降。 

目標：建立一個以文字資料為主的搜尋系統
1. 使用 Boolean Search 與 Prefix Search，結合關鍵字排序，使搜尋結果有更大的彈性與相關性。
2. 針對搜尋流程使用 List、Hash Map、Trie 三種不同資料結構進行實作，分析在不同資料規模下的效能差異。

### 競品比較
<!-- 比較目前已經存在可取得的類似工具或應用 -->
> **◎** = 最接近  
> **×** = 不相關  

| 比較項目 | Ctrl + F | Multiple Search and Highlight | 文字搜尋系統 |
|---|---|---|---|
| 關鍵字搜尋 | ◎ | ◎ | ◎ |
| Boolean Search | × | × | ◎ |
| Prefix Search | × | × | ◎ |
| 搜尋結果排序 | × | × | ◎ |
| List | ◎ | ◎ | ◎ |
| Hash Map | × | × | ◎ |
| Trie | × | × | ◎ |

1. 瀏覽器內建搜尋：Ctrl + F  
    (1)運行環境：網頁瀏覽器  
    (2)搜尋對象：頁面的文字內容  
    (3)使用結構設計 : 近似List  
    (4)功能:    
    - 單一關鍵字搜尋  
    - 有逐筆跳轉功能，可快速瀏覽搜尋結果  

2. Chrome 擴充工具：Multiple Search and Highlight  
    (1)運行環境：Google Chrome 瀏覽器  
    (2)搜尋對象：頁面的文字內容   
    (3)使用結構設計 : 近似List  
    (4)功能:    
    - 多關鍵字搜尋  
    - 有顏色標記，可快速辨識不同關鍵字  
    - 顯示各關鍵字出現的次數     

### 預期功能  
<!-- 列出預計實作的功能 -->
1. 基本搜尋功能
2. 搜尋方法：
- Boolean Search(布林搜尋)
- Prefix Search(前綴詞搜尋)
3. 關鍵字相關性與排序
4. 不同資料結構的搜尋效能(複雜度)比較
- 資料量
- 查詢次數
- 查詢內容  

### 使用技術
<!-- 使用的語言、框架、工具等 -->
- 開發環境：Jupyter Notebook  
- 程式語言：Python  
- 搜尋對象：以英文文字資料為主  
- 視覺化工具：Matplotlib (圖表分析)  

### Prototype 預計可驗證內容 
1. 完成基本搜尋系統架構  
   - 可讀.txt資料
   - 指定關鍵字查詢  
   - 可回傳是否存在  
2. 實作List（線性搜尋）、Hash Map搜尋功能  
3. 初步測試：比較List與Hash Map的搜尋效能

---

## Prototype Report
### 目前進度
<!-- 完成了什麼 -->
1. 完成基本搜尋系統架構  
   - 可讀.txt資料
   - 指定關鍵字查詢  
   - 可回傳是否存在  
2. 實作List（線性搜尋）、Hash Map搜尋功能
3. 初步測試：比較List與Hash Map的搜尋效能
4. 實作Boolean Search

### 遇到的困難
<!-- 遇到什麼問題、如何解決或打算如何解決 -->
文章處理部分：
1. 文章中間換行與多餘空白影響切句與結果顯示。目前是只能處理文章前後空白，如果文章中間有奇怪的換行，在顯示時會跑錯或看起來很奇怪。
- 預計解決 : 新增讀檔後將連續空白、換行與tab全部轉乘成單一空格的功能。

2. 現在切句方式以「句尾標點後有空白」來判斷。只有在句尾標點後面有空白時才會切句，如果句號後面直接接另一單字，分句會錯。
- 預計解決 : 在句尾標點後直接接大寫字母時補上空格，再進行切句。

Boolean Search：
1. 目前是無論AND先還是OR先，都只有由左到右判斷，但是正常的邏輯來看應該要讓AND先、再判斷OR。
- 預計解決 : 加入新的判斷：若無括號，則AND先、OR後；有括號，則優先判斷括號內的內容

### 下一步計畫
<!-- 接下來要做什麼 -->
1. 斷詞與切句問題的解決
2. 處理Boolean Search判斷的先後順序
3. 實作Prefix Tree

### 與課程的關聯
<!-- 到目前為止，你的實作中哪些部分與課程內容有關？關係是什麼？ -->
1. List/Array
- 使用一維與二維List儲存不同階段的文字資料
    - 一維 : sentences(切句後的句子)、vocab_list(單字表)
    - 二維 : sentence_tokens(斷詞後的結果:sentences*tokens)
2. Hash Map/ Hash Table : 由Python dict透過 hash function 將key對應到hash table中的位置
- 在結果輸出部分 : 搜尋結果以dictionary形式回傳 : 以key-value結構，可以在顯示結果時，直接用key找到對應value
- 在關鍵字查詢部分 : dict_search() : 使用前面就建立好的vocab_dict，就可以在搜尋關鍵字時，把單字表內的單字作為key，value設為True，要查詢時則判斷關鍵字是否為dict中的key
3. Linear Search
- list_search() : 用線性搜尋來判斷，我要找的關鍵字是否存在

---
## Final Report
### 專案說明
<!-- 完整描述你的專案做了什麼 -->
以 Python library 的形式實作兩個模組：text_search，文字搜尋系統本身，以及compare_tools，效能分析。
主要的功能在於布林搜尋，透過條件組合，尋找「符合特定語意條件的內容」。
定位：文件內的閱讀輔助搜尋工具。
text_search
- 基本搜尋 : 查詢單字或完整片語(兩個以上連續的單字)
- Boolean search，處理帶有括號的條件查詢。透過條件組合，查找「符合特定語意條件的內容」。
- Prefix search，以文字的開頭找出其他可能的單字
- 關鍵字排序 : 以句子中出現該關鍵詞的頻率做排序，出現愈多次排序愈前面
- 以句子為單位輸出，以[]標示該次查詢之單字

compare_tools
- 將 query 分成存在與不存在的單字，觀察不同資料結構在text_search下的搜尋效率表現。

### 使用方式
<!-- 如何編譯、執行、使用你的程式 -->
以Python library的形式提供，使用者import此文字搜尋系統的library，並且可使用以下函式來進行文章內的查找 : 
text_search
- .get_article_info() : 用以看文章的資訊：句子數量與總詞數
- .search(query) : 進行單字搜尋或完整片語搜尋
- .search_with_boolean(query) : 用AND、OR、括號()，縮小搜尋範圍，找出符合條件的句子
- .search_prefix(prefix) : 以前綴搜尋並列出符合的單字
搜尋結果以句子為單位輸出，命中的單字或片語以[]標示

compare_tools
- compare_search_speed() : 比較 List、Hash Map、Trie 三種資料結構的搜尋效率
- show_search_speed_comparison_chart() : 將比較結果畫成長條圖

### 與課程的關聯總結
<!-- 總結你的專題與進階程式設計及資料結構課程之間的關聯 -->
text_search : 
- List / Array : 
- 使用一維與二維List儲存文字處理後的資料。
- 一維 : _sentences(切句後的句子)、_vocab_list(單字表)。
- 二維 : _sentence_tokens(斷詞後的結果:sentences*tokens)。

- Hash Map/ Hash Table : 由Python dict透過hash function將key對應到hash table中的位置。
- 結果輸出 : 用dictionary儲存搜尋結果與比較結果。
- 關鍵字查詢 : 用_vocab_dict快速判斷單字是否存在。

- Sorting : 
- 搜尋結果依出現次數，由大到小排序。
- 前綴搜尋結果依照在文章中的出現次數，由大到小排序。

- Tree : 
- 前綴搜尋使用Trie實作。Trie是一種多路樹，每個節點可連接多個子節點。

- Recursion : 
- 用遞迴做DFS，找符合prefix的單字。
- Boolean Search，處理括號中的巢狀布林條件。

compare_tools : 
- 演算法分析
- 比較不同資料結構在相同任務下的效能差異。比較list、dict、trie，在同一批 query 下的搜尋速度。
- 將query分成存在與不存在的單字，比較不同資料結構在命中與未命中情況下的搜尋效率。
