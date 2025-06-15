# WikipediaNetwork Node Classification

## 🚀 Giới thiệu

Dự án này khám phá bài toán **Phân loại Nút (Node Classification)** trên tập dữ liệu đồ thị **WikipediaNetwork**. Mục tiêu chính là phân loại các thực thể/bài viết Wikipedia dựa trên cấu trúc đồ thị và các đặc trưng của chúng, tận dụng sức mạnh của các mô hình Học sâu trên Đồ thị (Graph Neural Networks - GNNs).

## 🎯 Lĩnh vực & Bài toán

* **Lĩnh vực:** Học máy trên đồ thị, Xử lý ngôn ngữ tự nhiên (liên quan đến đặc trưng văn bản), Phân tích mạng.
* **Bài toán:** Phân loại Nút (Node Classification) - Gán nhãn cho từng nút (bài viết Wikipedia) trong đồ thị.

## ✨ Mô hình Sử dụng

Dự án triển khai mô hình **Graph Neural Network (GNN)**, cụ thể là `DirGNNConv`, để xử lý cấu trúc đồ thị có hướng của WikipediaNetwork.

* **Lý do lựa chọn `DirGNNConv`:**
    * **Bản chất đồ thị có hướng:** WikipediaNetwork là một đồ thị có hướng, nơi các liên kết giữa các bài viết có chiều (ví dụ: liên kết từ A đến B không ngụ ý liên kết ngược lại từ B đến A).
    * **Tối ưu hóa thông tin hướng:** Các GNN truyền thống thường được thiết kế cho đồ thị vô hướng hoặc bỏ qua thông tin hướng, dẫn đến mất mát thông tin quan trọng. `DirGNNConv` được thiết kế đặc biệt để khai thác và tận dụng thông tin hướng trong đồ thị, giúp cải thiện đáng kể hiệu suất phân loại trên các tập dữ liệu có hướng phức tạp.

## 📁 Cấu trúc Dự án

Dự án được tổ chức gọn gàng trong một tệp Jupyter Notebook duy nhất (`ProjectImplementation.ipynb`), bao gồm các giai đoạn phát triển chính:

1.  **Thu thập & Tiền xử lý dữ liệu:** Tải về và chuẩn bị tập dữ liệu WikipediaNetwork cho quá trình huấn luyện.
2.  **Phân tích & Thăm dò dữ liệu:** Khám phá các đặc điểm thống kê của tập dữ liệu (số lượng nút, cạnh, phân bố lớp) để hiểu rõ hơn về cấu trúc dữ liệu.
3.  **Huấn luyện Mô hình:** Xây dựng, cấu hình và tiến hành huấn luyện mô hình `DirGNNConv`.
4.  **Đánh giá Hiệu suất Huấn luyện:** Phân tích kết quả huấn luyện bằng các chỉ số hiệu suất như độ chính xác (accuracy) và ma trận nhầm lẫn (confusion matrix).
5.  **Kiểm định trên Tập Test:** Đánh giá khả năng khái quát hóa của mô hình trên tập dữ liệu kiểm thử hoàn toàn mới.

## 🛠️ Yêu cầu Hệ thống

Để chạy dự án này, bạn cần cài đặt các thư viện sau:

* Python 3.x
* [PyTorch](https://pytorch.org/)
* [PyTorch Geometric](https://pytorch-geometric.readthedocs.io/en/latest/): Một thư viện mạnh mẽ cho GNNs trên PyTorch.
* Các thư viện phân tích dữ liệu và visualization cơ bản: `numpy`, `pandas`, `matplotlib`, `seaborn`.

## 🚀 Hướng dẫn Sử dụng

Thực hiện các bước sau để chạy dự án:

1.  **Sao chép Kho lưu trữ (Clone the repository):**
    ```bash
    git clone <URL_TO_YOUR_REPOSITORY>
    cd <YOUR_REPOSITORY_NAME>
    ```
2.  **Cài đặt các gói phụ thuộc:**
    ```bash
    pip install torch torchvision torchaudio
    pip install torch_geometric  # Tham khảo hướng dẫn cài đặt chi tiết nếu gặp lỗi: [https://pytorch-geometric.readthedocs.io/en/latest/install/installation.html](https://pytorch-geometric.readthedocs.io/en/latest/install/installation.html)
    pip install numpy pandas matplotlib seaborn
    ```
3.  **Mở Jupyter Notebook:**
    ```bash
    jupyter notebook ProjectImplementation.ipynb
    ```
4.  **Chạy các ô (cells) trong Notebook theo thứ tự** để xem toàn bộ quy trình từ tải dữ liệu đến đánh giá mô hình.

## 🧑‍💻 Tác giả

* **Võ Huỳnh Thanh Phương**
* Mã số sinh viên: 2151013072

## 📚 Tham khảo

Dự án này được xây dựng và lấy cảm hứng từ các nguồn tài nguyên và nghiên cứu sau:

* [PyTorch Geometric Documentation](https://pytorch-geometric.readthedocs.io/en/latest/)
* [Dir-GNN: Graph Neural Networks for Directed Graphs (GitHub Repository)](https://github.com/emalgorithm/directed-graph-neural-network)
* [Wikipedia Network Dataset (PyTorch Geometric)](https://pytorch-geometric.readthedocs.io/en/latest/generated/torch_geometric.datasets.WikipediaNetwork.html)
