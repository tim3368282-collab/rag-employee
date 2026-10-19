# rag-employee
A RAG-based question answering system using BGE-M3, Qdrant and Qwen2.5.
RAG 員工手冊智慧問答系統
專案介紹

本專案使用 Python 建置檢索增強生成（Retrieval-Augmented Generation, RAG）問答系統，透過文件切分、文字向量化、向量資料庫檢索與大型語言模型生成回答，實作制度文件的自然語言查詢。

使用技術
```text
Python
BGE-M3：文字向量化
Qdrant：向量儲存與相似度檢索
Qwen2.5-3B-Instruct：生成式問答
Hugging Face Transformers
Sentence Transformers
系統流程
讀取並解析制度文件。
依照章節與條文進行 Chunking。
使用 BGE-M3 將文件內容轉換成向量。
將向量與文件 metadata 儲存至 Qdrant。
根據使用者問題檢索相關文件片段。
將檢索內容與問題組合成 Prompt。
使用 Qwen 依據提供的文件內容生成回答。
```

實作成果
```text
系統已完成以下問答測試：

問題：特休有幾天？
結果：依照文件內容，整理不同工作年資對應的特別休假天數。
問題：婚假有幾天？
結果：婚假為八天。
問題：試用期多久？
結果：試用期為三個月。
```
以上為目前的測試案例，實際回答依據檢索到的文件內容產生。

學習與後續改進

透過本專案實作文件前處理、Embedding、向量資料庫及大型語言模型整合，了解 RAG 問答系統的基本架構。

後續可進一步評估不同 Chunking 策略、檢索參數與模型選擇對問答品質的影響，並建立更完整的測試資料集。

執行環境

主要程式與操作流程請參考 rag_employee_qa.ipynb。

本專案使用的模型、Python 套件與硬體需求，請依 Notebook 中的實際設定安裝與配置。
