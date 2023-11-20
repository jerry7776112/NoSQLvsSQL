# NoSQLvsSQL
## NoSQL vs. SOL

### 1. What actually is a database?
* **A systematic collection of data**:在電腦的世界中，可以以電子的方式訪問數據集合。
* 一個資料庫是一個組織良好的資訊集合，可透過電腦系統進行存儲、管理和檢索。資料庫可以包含多個表，每個表都包含一組相關的數據。每個表都有一個主鍵，用於唯一識別表中的每個記錄(ex: ID)。資料庫可使用SQL等語言進行查詢和操作，以滿足不同的需求。
* 主要有四種操作方式: GET Data, Add Data, Delete Data, Update Date
* Small Digital Storage: SD Card, Hard Drive, USB
* Large Digital Storage: Computer Cluster, Cloud Storage
* File System: 儲存在位於設備上的東西，例如: 硬碟
* Cluster: 多個硬碟等等整合組成，只需要一個控制介面即可執行所有
* Database Model Common Types:
    * Relational
    * Wide-column
    * Document
    * Key-Value
### 2. What is a database management system?

我們與資料庫本質上進行通訊的一種方式，可執行GET Data, Add Data, Delete Data, Update Date這些操作。

### 3. What is ACID?
ACID 是指資料庫管理系統在寫入或更新資料的過程中，為保證交易是正確可靠的，所必須具備的四個特性：原子性(不可分割性)、一致性、隔離性和持久性。
*	**原子性(不可分割性)(atomicity)**：指一個事務中的所有操作，要麼全部完成，要麼全部不完成，不會停留在中間某個狀態。
*	**一致性(consistency)**：指一個事務完成後，資料庫中的資料必須保持一致性狀態。
*	**隔離性(isolation)**：指一個事務的執行不受其他事務的干擾，多個事務之間互不干擾。
*	**持久性(durability)**：指一個事務完成後，對系統的修改是永久性的，即使系統發生故障也不會丟失。

ACID通常用於需要高度正確性和一致性的應用，例如銀行轉帳、訂票系統等。

### 5. Relational databases
關聯式資料庫是一種數據庫，它將數據組織成行和列，這些行和列共同形成一個表。數據通常跨多個表結構，這些表可以透過主鍵或外鍵進行聯接。關聯式資料庫通常使用SQL語法來進行資料的查詢。
**優點:**
*	一致性：數據在整個關聯式數據庫中保持一致。數據完整性，即手頭數據的準確性和完整性，通過完整性約束（類似於規則執行程序）在關聯式數據庫中得到強制執行。
*	隔離性：每個事件都是獨立的，不受其他事件的影響。
*	可靠性：關聯式數據庫的設計使其更加可靠。它們具有較高的安全性和完整性，並且可以通過備份和復原來保護數據。
*	易於使用：關聯式數據庫使用結構化查詢語言（SQL）來管理和查詢數據。SQL是一種易於學習和使用的語言，並且可以通過多種軟體和工具進行操作。

**缺點:**
*	**可擴展性**：關聯式數據庫的可擴展性受到限制。當數據庫變得太大時，它們可能會變得不穩定或無法處理。
*	**複雜性**：關聯式數據庫的設計使其更加複雜。它們需要較長的時間來設計和實施，並且需要更多的硬體和軟體資源來運作。
*	**性能**：關聯式數據庫的性能可能會受到影響，特別是在處理大量數據時。這可能會導致查詢速度變慢或數據庫變得不穩定。

### 6. Non-relational databases
非關聯式數據庫不使用關聯表格的結構化數據概念，而是使用鬆散的模式或無模式來存儲數據。
**優點:**
*	**可擴展性**：非關聯式數據庫的可擴展性更高。當數據庫變得太大時，它們可以更好地處理和擴展。
*	**靈活性**：非關聯式數據庫的設計使其更加靈活。它們可以處理各種不同類型的數據，而不需要修改架構。
*	**性能**：非關聯式數據庫的性能通常比關聯式數據庫更好，特別是在處理大量數據時。

**缺點:**
*	**複雜性**：非關聯式數據庫的設計使其更加複雜。它們需要較長的時間來設計和實施，並且需要更多的硬件和軟件資源來運行。
*	**一致性**：非關聯式資料庫的數據一致性通常比關聯式資料庫差。這是因為它們通常不使用事件來保證數據的一致性。
*	**學習曲線**：非關聯式數據庫通常需要學習新的查詢語言和技術，這可能需要更長的時間來學習和掌握。

### 7. Pros and Cons: Comparing RDBMS and NoSQL
| 類型 | RDBMS | NoSQL |
|:-----:|-------|-------|
| **定義**   |  關聯式資料庫  |  非關聯式資料庫 |
| **資料表** |由多個資料表所組成，並且可以將資料表關聯起來|由多個 collection 所組成，每個 collection 中每筆資料為一份 document，document 的資料格式不需一致 |
| **Schema** |必須先定義好，並且只接受同樣格式資料的插入與修改。|不需要定義 schema、沒有關聯的關係。|
| **查詢**  |可以使用 SQL (Structured Querying Language) 來管理及查詢資料，可以使用 JOIN 來連結多個資料表，做較複雜的查詢。|不支援 SQL，但可以使用其他查詢語言，例如 MongoDB 的查詢語言。|
| **擴充性** |容易做 vertical scaling，但較不容易做 horizontal scaling。|容易做 horizontal scaling。|
| **ACID 特性**  |具備 ACID 特性，保證了資料的一致性。|沒有保證 ACID 的特性。|

### 8. Wide Column Database
Wide Column Database 是一種 NoSQL 資料庫，也被稱為 wide-column store 或 extensible record store。它使用表格、列和欄，**但與關聯式資料庫不同的是，同一個表格中的列的欄名和格式可以因列而異**。Wide Column Database 可以被解釋為一個二維的鍵值儲存庫。 
Wide Column Database 和 columnar database 不同，前者的欄位名稱和格式可以因列而異，而後者則使用欄狀數據佈局，每個欄位都單獨存儲在硬碟上。Wide Column Database 通常支援列族的概念，但每個列族通常包含多個一起使用的欄位，類似於傳統的關聯式資料庫表格。在給定的列族中，所有資料都是以逐行方式存儲的，因此給定行的欄位是一起存儲的，而不是每個欄位都單獨存儲。支援列族的 Wide Column Database 也稱為列族資料庫。
常見的相關資料庫:
*	Apache Cassandra
*	Bigtable
*	Hypertable
*	Azure Tables

**優點：**
*	可擴展性：Wide Column Database 可以輕鬆地擴展以處理大量數據，而不需要對現有架構進行更改。
*	高效性：Wide Column Database 可以快速地處理大量數據，並且可以在多個節點上進行分佈式處理。
*	彈性：Wide Column Database 允許用戶在表格中添加或刪除列，而不需要對現有數據進行更改。
缺點：
*	複雜性：架構比傳統的關聯式資料庫更複雜，需要更多的管理和維護。
*	不支援複雜查詢：不支援複雜的 SQL 查詢，因此需要使用其他工具來進行數據分析。
*	不支援 ACID 特性：不支援 ACID（一致性、隔離性和持久性）特性，代表可能不適合需要高度一致性和可靠性的應用程序。

### 9. Document Database
是一種 NoSQL 資料庫，它以文件為基礎來儲存資料。文件資料庫提供了多種優點，包括：
*	直覺的資料模型: 對於開發人員來說快速且容易使用。
*	靈活的架構: 允許資料模型隨著應用程式需求的變化而演進。
可橫向擴展的能力。
*	文件資料庫不同於關聯式資料庫:它不是以固定的列和欄來儲存資料，而是使用靈活的文件。

文件是文件資料庫中的一個記錄。文件通常存儲有關一個物件及其相關元數據的信息。文件以字段-值對的形式存儲數據。值可以是各種類型和結構，包括字符串、數字、日期、數組或對象。文件可以以 JSON、BSON 和 XML 等格式存儲。

**優點：**
*	直覺的資料模型: 對於開發人員來說快速且容易使用。
*	靈活的架構: 允許資料模型隨著應用程式需求的變化而演進。
*	可橫向擴展的能力。

**缺點：**
*	不支援複雜的 SQL 查詢。
*	不支援 ACID（一致性、隔離性和持久性）。
*	不適合用於需要高度正規化的資料。

### 10.	Key-Value Database
是一種 NoSQL 資料庫，它將資料以「鍵-值」的方式儲存，並優化讀寫操作。資料可以透過唯一的鍵或多個唯一的鍵檢索，以檢索與每個鍵相關聯的值。值可以是簡單的資料類型，例如字符串和數字，也可以是複雜的對象。特點：
*	以鍵值對的形式儲存資料適合儲存大量的非結構化資料。
*	操作簡單支持快速查詢、插入、更新和刪除操作。
*	可擴展到大型分佈式系統支持高可用性和高可擴展性。
*	可根據需要進行水平擴展，以應對不斷增長的數據量。
*	可與其他 NoSQL 資料庫和關聯式資料庫進行整合，以滿足不同的應用需求。
**優點：**
*	以鍵值對的形式儲存資料，適合儲存大量的非結構化資料。
*	操作簡單，支持快速查詢、插入、更新和刪除操作。
*	可擴展到大型分佈式系統，支持高可用性和高可擴展性。
*	可根據需要進行水平擴展，以應對不斷增長的數據量。
*	可與其他 NoSQL 資料庫和關聯式資料庫進行整合，以滿足不同的應用需求。
**缺點：**
*	不支援複雜的查詢和多表關聯操作，不適合儲存結構化資料。
*	不支援ACID，無法保證資料的一致性和完整性。
*	需要手動處理資料的序列化和反序列化，增加了開發和維護的成本。
*	不支援多版本並發控制（MVCC），可能會導致資料的丟失或不一致。

### 11. Multi-Model Databases
是一種資料庫管理系統，目的為支援多種資料模型。以下是多模型資料庫的特點：
*	可支援多種資料模型，如文件、圖形、關聯和鍵值模型。
*	可在單個集成後端中存儲和查詢多種資料模型。
*	可提供更靈活的資料存儲和查詢選項，並且可以根據需要使用不同的資料模型。

多模型資料庫的出現是為了解決傳統資料庫管理系統只支援單一資料模型的問題。多模型資料庫可以更好地滿足不同應用場景的需求，並且可以提供更靈活的資料存儲和查詢選項。
**優點：**
*	支援多種資料模型，可以更好地滿足不同應用場景的需求。
*	可提供更靈活的資料存儲和查詢選項，並且可以根據需要使用不同的資料模型。
*	可在單個集成後端中存儲和查詢多種資料模型。

**缺點：**
*	資料庫的複雜性會增加，因為需要支援多種資料模型。
*	需要更多的資源來支援多種資料模型。
*	可能會導致資料庫的效能下降。

### 12. Use cases: When to use RDBMS or NoSQL
*	RDBMS 稱為關係資料庫，而 NoSQL 稱為分散式資料庫。
*	RDBMS 使用結構化數據來識別主鍵，而 NoSQL 使用非結構化數據。
*	RDBMS資料庫更適合使用SQL進行複雜的查詢和數據操作，而NoSQL資料庫更適合簡單的查詢，適合數據關係不太複雜的專案。
