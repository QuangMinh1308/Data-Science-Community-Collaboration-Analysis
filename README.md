# 
# 📘 Data-Science-Community-Collaboration-Analysis 
*(Phân tích cộng đồng nghiên cứu & phát hiện nhóm hợp tác trong lĩnh vực Khoa học Dữ liệu)*

![GitHub Repo stars](https://img.shields.io/github/stars/HoangQuangMinh/Data-Science-Community-Collaboration-Analysis?style=flat-square&color=yellow)
![GitHub contributors](https://img.shields.io/github/contributors/HoangQuangMinh/Data-Science-Community-Collaboration-Analysis?style=flat-square&color=blue)
![GitHub last commit](https://img.shields.io/github/last-commit/HoangQuangMinh/Data-Science-Community-Collaboration-Analysis?style=flat-square&color=green)
![GitHub issues](https://img.shields.io/github/issues/HoangQuangMinh/Data-Science-Community-Collaboration-Analysis?style=flat-square&color=orange)
![GitHub license](https://img.shields.io/github/license/HoangQuangMinh/Data-Science-Community-Collaboration-Analysis?style=flat-square&color=red)

---

## 📌 Overview  
*(Tổng quan)*  
This project analyzes research collaboration patterns in the **Data Science** field by building a large-scale **co-author network** using data collected from **OpenAlex**. Community detection algorithms (Louvain, Leiden, Fast Greedy) are applied to uncover research groups and influential authors.  
*(Dự án phân tích mô hình hợp tác nghiên cứu trong lĩnh vực Khoa học Dữ liệu bằng cách xây dựng mạng đồng tác giả từ OpenAlex và áp dụng các thuật toán phát hiện cộng đồng.)*

---

## ✨ Objectives  
*(Mục tiêu)*  
- Build a **co-author network** representing scientific collaborations.  
- Apply **community detection** algorithms (Louvain, Leiden, Fast Greedy).  
- Compute **centrality metrics** (Degree, Betweenness, Closeness, Eigenvector).  
- Visualize and evaluate the structure of scientific collaboration.  
- Identify **influential authors** and **core research clusters**.  

---

# 🧩 Dataset  
*(Dữ liệu)*  

The dataset was collected through **OpenAlex API**, focusing on the Data Science domain (concept ID: `C2522767166`).  
*(Dữ liệu thu thập qua OpenAlex API, tập trung vào lĩnh vực Khoa học Dữ liệu.)*

**Key fields included:**  
- `Work_ID`  
- `Title`  
- `Year`  
- `Cited_by` (citation count)  
- `Authors`, `Author_IDs`  
- `Concepts`  

**Example cleaned dataset (from paper):**

| Work_ID | Title | Year | Cited_by | Authors | Author_IDs |
|--------|-------|------|----------|---------|------------|
| W2144634347 | Molecular Cloning: A Laboratory Manual | 2001 | 133,517 | Joseph Sambrook; Elisabeth Fritsch; Tom Maniatis | A5112152140; ... |
| W4300870773 | Statistical Power Analysis for the Behavioral Sciences | 1989 | 83,956 | Keith E. Muller; Jacob Cohen | A5110163574; ... |

*(Bảng minh họa dữ liệu đã được làm sạch.)*

---

# 🏗 Methodology  
*(Phương pháp nghiên cứu)*

### 1. Data Collection & Preprocessing  
- Collect Data Science papers via OpenAlex API.  
- Remove duplicates & missing values.  
- Extract author list → build co-author edges.  
- Normalize author identifiers.  

### 2. Build Co-Author Network  
- Graph **G = (V, E)** where:  
  - Node = Author  
  - Edge = Co-authorship  
  - Weight = # of collaborations  

### 3. Apply Community Detection Algorithms  
- **Louvain**  
- **Leiden**  
- **Fast Greedy** (Clauset–Newman–Moore)  

### 4. Compute Centrality Scores  
- Degree  
- Betweenness  
- Closeness  
- Eigenvector  

### 5. Visualization  
- Colored communities  
- Node size scaled by centrality  
- Force-directed graph layout  

---

# 📊 Co-Author Network Statistics  
*(Thống kê mạng đồng tác giả)*

| Metric | Value |
|--------|-------|
| Nodes | 9,212 |
| Edges | 136,198 |
| Density | 0.0032 |
| Avg Degree | 29.57 |
| Clustering Coefficient | 0.8608 |

(Cho thấy đây là mạng lớn, thưa nhưng liên kết nội bộ mạnh.)

---

# 🥇 Community Detection Comparison  
*(So sánh thuật toán phát hiện cộng đồng)*

### 📌 Comparison Table  
*(Bảng so sánh)*

| Algorithm | Communities | Modularity (Q) | Strengths | Weaknesses |
|-----------|-------------|----------------|-----------|------------|
| **Louvain** | 1,167 | 0.9416 | Fast, scalable, high modularity | Resolution limit |
| **Leiden** | 1,167 | ⭐ **0.9418 (highest)** | Well-connected communities, stable | Slightly more complex |
| **Fast Greedy** | 1,164 | 0.9344 | Produces hierarchy (dendrogram) | Lower modularity, slower on big graphs |

### ⭐ Summary  
- **Leiden** achieves the *best* modularity and stability.  
- **Louvain** is nearly equal, extremely fast.  
- **Fast Greedy** is good for hierarchical analysis.

*(Leiden tốt nhất, Louvain nhanh nhất, Fast Greedy tốt cho phân cấp.)*

---

# 🧠 Centrality Analysis  
*(Phân tích chỉ số trung tâm)*

### Authors with highest:  
- **Degree Centrality:** Michelle Giglio, Ricardo Silva, Pascale Gaudet  
- **Betweenness Centrality:** John P. A. Ioannidis (top “bridge”)  
- **Closeness Centrality:** Asif Chinyavalla, Sandra W. Clifton  
- **Eigenvector Centrality:** Chris Mungall, Karen Christie  

*(Những tác giả có tầm ảnh hưởng nhất theo từng chỉ số.)*

---

# 📈 Visualizations  
*(Trực quan hóa)*

This project visualizes:  
- Top 2000-author network  
- Largest 10 communities  
- Centrality distributions  
- Algorithm comparison charts  

*(Biểu đồ cấu trúc mạng, cộng đồng và chỉ số ảnh hưởng.)*

---

# 📚 Discussion  
*(Thảo luận)*  

Key findings:  
- Data Science research forms **hub–spoke structures**.  
- Strong community separation (Q ≈ 0.94).  
- Some authors act as “knowledge bridges” across areas.  
- Leiden is the most stable and accurate method.  
- Fast Greedy is useful for hierarchical clustering.  

*(Các cộng đồng lớn hoạt động như hạt nhân lan tỏa tri thức.)*

---

# 🏁 Conclusion  
*(Kết luận)*

This research demonstrates the effectiveness of combining:  
- community detection,  
- centrality analysis,  
- scientific collaboration modeling  

to uncover hidden structures in the Data Science ecosystem.

Future extensions may include:  
- dynamic network analysis,  
- topic modeling integration,  
- graph neural networks (GNNs).

---

# 📄 Reference  
*(Tài liệu tham khảo — xem đầy đủ trong PDF)*  
Source: full report extracted from uploaded file. :contentReference[oaicite:2]{index=2}  

---


