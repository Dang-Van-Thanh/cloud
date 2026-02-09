---
title: "HƯỚNG DẪN THỰC HIỆN BÀI TẬP LỚN"
subtitle: |
  HỌC PHẦN DỮ LIỆU LỚN, KHAI PHÁ DỮ LIỆU; KHAI PHÁ DỮ LIỆU -  
  HỌC KÌ II NĂM HỌC 2025–2026
author: "ThS. Lê Thị Thùy Trang"
date: "2025-12-23"
output: 
  bookdown::pdf_document2:
    latex_engine: lualatex
    toc: false
    classoption: oneside

geometry: "includeheadfoot,centering,margin=2cm,bindingoffset=0pt"

header-includes: |
  \usepackage{xcolor}
  \usepackage{graphicx}
  \usepackage{float}
  \usepackage{fontspec}
  \setmainfont{Times New Roman}
  \usepackage{indentfirst}
  \setlength{\parindent}{2em}
  \usepackage{comment}
  \usepackage{fancyhdr}
  \usepackage{longtable}
  \usepackage{array}
  \usepackage{multirow}
  \usepackage{tikz} 
  \usetikzlibrary{arrows.meta, positioning, shapes.multipart}
  \pagestyle{fancy}
  \fancyhf{}
  \lhead{Final Project Data mining}
  \rhead{Lê Thị Thùy Trang}
  \cfoot{\thepage}
  \renewcommand{\headrulewidth}{0.4pt}
  \renewcommand{\footrulewidth}{0.4pt}
---

# Mục tiêu của bài tập lớn 

## Về mặt kiến thức:

Sinh viên vận dụng kiến thức về khám phá dữ liệu (EDA), tiền xử lý, trích xuất/thiết kế đặc trưng, và các kỹ thuật khai phá dữ liệu đã học để xây dựng pipeline khai phá và đánh giá kết quả một cách khoa học.
  
Bài tập lớn tập trung vào các nhóm bài toán

\begin{itemize}
  \item Khai phá mẫu/tri thức (association patterns)

  \item Phân cụm (clustering + diễn giải cụm)

  \item Phân lớp (classification) và bán giám sát khi thiếu nhãn

  \item Hồi quy/chuỗi thời gian (nếu đề tài thuộc nhóm dự báo)
\end{itemize}

## Về mặt kỹ năng:
  
  - Rèn luyện kỹ năng cốt lõi của một người làm dữ liệu: tiền xử lý, tạo đặc trưng, thử nghiệm–so sánh phương pháp và trình bày kết quả theo lập luận khoa học.
  
  - Rèn luyện kỹ năng làm việc nhóm, nghiên cứu, viết báo cáo và thuyết trình dự án.

# Yêu cầu chung

Sinh viên làm việc theo nhóm từ $2$ đến $4$ thành viên. 

\textbf{Đề tài bài tập lớn} do giảng viên chỉ định theo danh sách đề bài ở phần \textcolor{blue}{\ref{subject}{danh sách đề tài}}.

Dataset sử dụng đúng link được cung cấp trong bảng đề tài; nhóm phải ghi rõ nguồn dữ liệu, mô tả cột, ý nghĩa nhãn/target (data dictionary).

Dự án \textbf{bắt buộc} thực hiện theo tinh thần "project repo": có cấu trúc thư mục rõ ràng, module hoá, chạy lại được (reproducible), KHÔNG sử dụng notebook rời rạc.

## Quy trình khai phá dữ liệu tổng quát


Quy trình tổng quát tuân theo logic “Nguồn dữ liệu → Tiền xử lý → Đặc trưng/biểu diễn → Mô hình → Đánh giá” như sau:

\begin{enumerate}

  \item Data Source (Nguồn dữ liệu): Dữ liệu dạng bảng/văn bản/ảnh/chuỗi thời gian/đồ thị… tùy đề tài.

  \item Preprocessing (Tiền xử lý): Làm sạch, xử lý thiếu, chuẩn hoá, mã hoá biến phân loại, cân bằng lớp (nếu cần), tạo session (log), resample (time series)…

  \item Feature / Representation (Đặc trưng/biểu diễn): TF-IDF/embeddings (text), đặc trưng ảnh, đặc trưng hành vi (RFM), lag features (chuỗi thời gian), graph features, vector hoá giỏ hàng…

  \item Mining / Modeling (Khai phá, mô hình hoá)
  
  \begin{itemize}
    \item Khai phá tri thức (bắt buộc): pattern mining / clustering / anomaly / rule extraction…
    \item Mô hình dự đoán (nếu đề tài có supervised): classification/regression/forecasting; ghi rõ hyperparams, thời gian train, thiết lập thực nghiệm 
    \end{itemize}
    
  \item Evaluation and Results (Đánh giá, kết quả): Dùng metric phù hợp, lập bảng/biểu đồ so sánh mô hình, kèm insight và khuyến nghị hành động.

  \item Nhánh bổ sung: Bán giám sát (Semi-supervised) – chỉ áp dụng khi đề tài là phân lớp

  \begin{itemize}
    \item Với đề tài phân lớp, nhóm phải thêm một nhánh thực nghiệm “thiếu nhãn”:
    \item Giữ lại p\% nhãn (p = 5/10/20), phần còn lại coi là unlabeled
    \item So sánh Supervised-only (ít nhãn) vs Semi-supervised (self-training/pseudo-label hoặc label spreading/propagation)
    \item Báo cáo learning curve theo \% nhãn và phân tích rủi ro pseudo-label
  \end{itemize}
\end{enumerate}

\begin{figure}[H]
  \centering
  \includegraphics[width=0.9\textwidth]{datamining_project.png}
  \caption{Pipeline project} 
\end{figure}


## Nội dung báo cáo (bắt buộc, theo đúng thứ tự)

Báo cáo phải có đủ các phần như sau:

\begin{enumerate}

  \item Đặt vấn đề và phân tích yêu cầu: bối cảnh, mục tiêu, tiêu chí thành công; mô tả dữ liệu và EDA.

  \item Thiết kế giải pháp và quy trình khai phá: mô tả pipeline; tiền xử lý; đặc trưng; lý do chọn kỹ thuật. 

  \item Phân tích mã nguồn và chức năng: tập trung mô tả kiến trúc repo, các module/class chính (DataCleaner/FeatureBuilder/Miner/Trainer/Evaluator…).

  \item Thử nghiệm và kết quả: metric phù hợp; bảng/biểu đồ so sánh các phương án.

  \item Thảo luận và so sánh: so sánh ưu/nhược; giải thích vì sao phương án A tốt hơn B; nêu thách thức gặp phải.

  \item Tổng kết và hướng phát triển: tóm tắt kết quả và đề xuất cải tiến.

\end{enumerate}

\textbf{Ghi chú:} Với nhóm có bán giám sát, phần (4)–(5) phải có thêm mục “thiếu nhãn: supervised vs semi-supervised”.


## Hình thức báo cáo 

Báo cáo viết bằng LaTeX theo template do giảng viên cung cấp hoặc \texttt{.docx} theo mẫu của trường

Khuyến khích: trình bày nhiều hình/bảng, ít “dán code”; code nằm trong repo.

## Sử dụng Github trong quá trình làm bài tập lớn

Sinh viên phải tổ chức project nhóm theo cấu trúc repo rõ ràng để đảm bảo dễ đọc – dễ chạy lại – dễ đánh giá. Repo cần tách bạch giữa dữ liệu, notebook báo cáo, mã nguồn (module), cấu hình tham số và kết quả đầu ra.

### Cấu trúc repo mẫu 

```bash
DATA_MINING_PROJECT/
├── README.md
├── requirements.txt            # hoặc environment.yml
├── .gitignore
├── configs/
│   └── params.yaml            # tham số: seed, split, paths, hyperparams...
├── data/
│   ├── raw/                   # dữ liệu gốc (không commit nếu quá lớn)
│   └── processed/             # dữ liệu sau tiền xử lý (ưu tiên parquet/csv)
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_preprocess_feature.ipynb
│   ├── 03_mining_or_clustering.ipynb
│   ├── 04_modeling.ipynb
│   ├── 04b_semi_supervised.ipynb   # CHỈ áp dụng cho đề tài có bán giám sát
│   └── 05_evaluation_report.ipynb
├── src/
│   ├── __init__.py
│   ├── data/
│   │   ├── __init__.py
│   │   ├── loader.py          # đọc dữ liệu, kiểm tra schema
│   │   └── cleaner.py         # xử lý thiếu, outlier, encoding cơ bản
│   ├── features/
│   │   ├── __init__.py
│   │   └── builder.py         # feature engineering (RFM, TF-IDF, lag, ...)
│   ├── mining/
│   │   ├── __init__.py
│   │   ├── association.py     # (nếu có) luật kết hợp / pattern
│   │   ├── clustering.py      # KMeans/HAC/DBSCAN + profiling
│   │   └── anomaly.py         # (nếu có) outlier/anomaly
│   ├── models/
│   │   ├── __init__.py
│   │   ├── supervised.py      # train/predict cho classification/regression
│   │   ├── semi_supervised.py # CHỈ áp dụng cho đề tài có bán giám sát
│   │   └── forecasting.py     # (nếu có) time series
│   ├── evaluation/
│   │   ├── __init__.py
│   │   ├── metrics.py         # accuracy, f1, auc, rmse, mae, ...
│   │   └── report.py          # tổng hợp bảng/biểu đồ kết quả
│   └── visualization/
│       ├── __init__.py
│       └── plots.py           # hàm vẽ dùng chung
├── scripts/
│   ├── run_pipeline.py        # chạy toàn bộ pipeline (khuyến khích)
│   └── run_papermill.py       # (khuyến khích) chạy notebook bằng papermill
├── outputs/
│   ├── figures/
│   ├── tables/
│   └── models/
└── reports/
    ├── final_report.pdf
```

### Quy ước đặt tên luồng pipeline

Notebook đặt theo thứ tự 01 → 05 để người chấm chạy/đọc theo pipeline.

\texttt{src/} chứa toàn bộ logic chính; notebook chỉ gọi hàm/lớp và trình bày kết quả.

Tất cả đường dẫn và tham số quan trọng đặt trong configs/params.yaml.

### Quy định về dữ liệu và lưu trữ 

Không commit dữ liệu lớn vào GitHub.

Nếu dataset nặng, nhóm phải cung cấp:

  - link dataset + hướng dẫn tải trong \texttt{README.md}, hoặc

  - script tải dữ liệu trong \texttt{scripts/} (nếu có thể).

### Yêu cầu tái lập

Repo được coi là đạt khi người khác có thể:

\begin{enumerate}

  \item \texttt{pip install -r requirements.txt}

  \item Cập nhật đường dẫn dữ liệu trong configs/params.yaml

  \item Chạy \texttt{ python  scripts/run\_papermill.py} 

  \item Thu được \texttt{outputs/} và hình/bảng đúng như báo cáo.
  
\end{enumerate}

## Điểm thưởng 

Có GUI/Demo app (Streamlit/Gradio/web nhỏ): cộng điểm theo mức hoàn thiện

# Danh sách đề tài bài tập lớn \label{subject}  

```{=latex}

\begingroup
% Tắt header/footer + số trang cho TẤT CẢ các trang mà longtable sinh ra
\pagestyle{empty}
\thispagestyle{empty}
\renewcommand{\headrulewidth}{0pt}
\renewcommand{\footrulewidth}{0pt}
\newgeometry{
  left=4mm,
  right=4mm,
  top=20mm,
  bottom=12mm,
  heightrounded
}

% --- Tuning để KHÔNG tràn phải và bám khung chữ ---
\setlength{\LTleft}{0pt}
\setlength{\LTright}{0pt}
\setlength{\LTpre}{0pt}
\setlength{\LTpost}{0pt}

\setlength{\tabcolsep}{1.9pt}      % giảm padding trong ô -> thêm bề ngang thực
\renewcommand{\arraystretch}{0.95} % giảm chiều cao hàng -> đỡ sát lề dưới
\footnotesize

\begin{longtable}{@{}|
  >{\raggedright\arraybackslash}p{0.095\linewidth}|
  >{\raggedright\arraybackslash}p{0.105\linewidth}|
  >{\raggedright\arraybackslash}p{0.135\linewidth}|
  >{\raggedright\arraybackslash}p{0.135\linewidth}|
  >{\raggedright\arraybackslash}p{0.125\linewidth}|
  >{\raggedright\arraybackslash}p{0.135\linewidth}|
  >{\raggedright\arraybackslash}p{0.16\linewidth}|
@{}}

\hline
Đề tài & Link dataset & Luật kết hợp & Phân cụm & Phân lớp & Bán giám sát & Hồi quy / Chuỗi thời gian \\
\hline
\endfirsthead

\hline
Đề tài & Link dataset & Luật kết hợp & Phân cụm & Phân lớp & Bán giám sát & Hồi quy / Chuỗi thời gian \\
\hline
\endhead

1. Phân tích doanh số siêu thị &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting}{Superstore Sales Dataset}} &
Chuẩn hoá giỏ hàng theo hoá đơn.\par
Chọn min\_support/min\_conf, xem lift.\par
Top luật + gợi ý combo/cross-sell. &
Đặc trưng RFM/giá trị/nhóm hàng.\par
Chuẩn hoá.\par
Hồ sơ cụm + insight. &
Dự đoán phân khúc (LogReg/DT/RF).\par
Đánh giá F1/ROC-AUC + phân tích lỗi. &
Không thực hiện đối với đề tài này \par &
Dự báo doanh số theo thời gian: split theo thời gian, baseline (naive/MA), ARIMA/Holt-Winters/Prophet, MAE/RMSE/sMAPE, phân tích residual/seasonality. \\
\hline

2. Dự đoán bệnh tim &
UCI/Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/redwankarimsony/heart-disease-data}{Heart Disease Dataset}} &
Rời rạc hoá chỉ số theo ngưỡng.\par
Apriori tìm tổ hợp triệu chứng.\par
Báo cáo support/conf/lift + diễn giải. &
Chuẩn hoá đặc trưng.\par
Mô tả cụm nguy cơ. &
Phân lớp nguy cơ (SVM/RF/XGB).\par
Imbalance: class\_weight/SMOTE.\par
Metric ưu tiên PR-AUC/F1 + phân tích lỗi. &
\emph{Tuỳ chọn (cân nhắc)} vì dữ liệu thường không quá lớn.\par
Nếu làm: giả lập 10--30\% nhãn, self-training với ngưỡng tin cậy cao, so sánh PR-AUC theo \% nhãn, phân tích nhóm khó. &
Hồi quy chỉ số (ví dụ huyết áp) theo yếu tố nguy cơ: Linear/Ridge vs XGBRegressor, MAE/RMSE, kiểm tra outlier/leakage; \emph{Không bắt buộc áp dụng chuỗi thời gian}. \\
\hline

3. Phân tích cảm xúc khách hàng &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/kritanjalijain/amazon-reviews}{Amazon Reviews Dataset}} &
Tách review tích cực/tiêu cực.\par
Apriori trên tập từ khoá/phrase.\par
Top luật + diễn giải chủ đề. &
TF-IDF/embeddings.\par
Topic/cluster (K-means/HDBSCAN).\par
Đặt tên cụm theo top terms.\par
Silhouette + ví dụ đại diện. &
Phân lớp sentiment (NB/LogReg/SVM/LSTM).\par
F1-macro + confusion matrix + phân tích lỗi (sarcasm, review ngắn). &
Giả lập ít nhãn, label spreading/self-training, learning curve theo \% nhãn, phân tích pseudo-label sai theo độ dài/độ hiếm từ. &
Hồi quy rating từ nội dung: baseline (Ridge/Linear) + mô hình mạnh (SVR/XGB), MAE/RMSE.\par
\emph{Không bắt buộc áp dụng chuỗi thời gian} \\
\hline

4. Phân tích giao dịch ngân hàng &
UCI: \textcolor{blue}{\href{https://archive.ics.uci.edu/dataset/222/bank+marketing}{Bank Marketing Dataset}} &
Tạo giỏ sản phẩm/dịch vụ theo khách.\par
Top luật cross-sell.\par
Đề xuất gói sản phẩm. &
Phân cụm hồ sơ tài chính.\par
Chuẩn hoá.\par
Đặt tên cụm. &
Dự đoán đăng ký term deposit (LogReg/RF/XGB).\par
Imbalance.\par
PR-AUC/F1 + giải thích đặc trưng. &
Giả lập 10--30\% nhãn, self-training, so sánh PR-AUC/lift@k theo \% nhãn, phân tích pseudo-label sai theo campaign/nhóm tuổi. &
Hồi quy số dư/tài chính theo tuổi/thu nhập: Linear/Ridge vs XGBRegressor, MAE/RMSE.\par
\emph{Không bắt buộc áp dụng chuỗi thời gian} \\
\hline


5. Dự báo thời tiết &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/muthuj7/weather-dataset}{Weather Dataset}}  &
Rời rạc hoá điều kiện.\par
Tìm điều kiện đồng xuất hiện.\par
So sánh theo mùa.\par
Top luật + diễn giải. &
Phân cụm ngày kiểu thời tiết.\par
Chuẩn hoá.\par
Hồ sơ cụm. &
Phân lớp loại thời tiết (RF/XGB).\par
F1-macro + phân tích lỗi giao mùa/cực trị. &
\emph{Không bắt buộc áp dụng học bán giám sát} &
Sử dụng chuỗi thời gian dự báo nhiệt độ/độ ẩm: ACF/PACF, ARIMA/Holt-Winters, MAE/RMSE, residual + outlier. \\
\hline

6. Phân tích hiệu suất nhân viên &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/anshika2301/hr-analytics-dataset}{HR Analytics Dataset}}  &
Rời rạc hoá yếu tố.\par
Tìm tổ hợp dẫn đến nghỉ việc.\par
So sánh lift giữa stay vs leave.\par
Gợi ý chính sách. &
Phân cụm nhân viên.\par
Chuẩn hoá.\par
Profiling cụm. &
Phân lớp nghỉ việc (XGB/RF).\par
PR-AUC/F1 + giải thích SHAP. &
Giả lập 10--30\% nhãn, self-training, so sánh PR-AUC theo \% nhãn, phân tích rủi ro gán nhãn sai (tác động chính sách). &
Hồi quy mức độ hài lòng/điểm hiệu suất (nếu có): MAE/RMSE, kiểm tra leakage.\par
\emph{Chuỗi thời gian thường không phù hợp} \\
\hline

7. Dự báo năng suất cây trồng &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/patelris/crop-yield-prediction-dataset/data}{Crop Yield datasets}} &
Rời rạc hoá điều kiện (đất/thời tiết/giống).\par
Apriori/ FP Growth tìm điều kiện đi kèm năng suất cao.\par
Top luật + khuyến nghị canh tác (mức mô tả). &
Phân cụm vùng trồng theo điều kiện.\par
Chuẩn hoá.\par
Profiling cụm + so sánh năng suất. &
Sử dụng cột \texttt{Yield} (biến liên tục) làm nhãn:ép kiểu số cho Yield, loại 
bản ghi Yield bị thiếu/0 bất thường. \par
Baseline + mô hình mạnh.\par
F1 + phân tích lỗi vùng hiếm. &
\emph{Không yêu cầu áp dụng học bán giám sát} &
Dự báo năng suất cây trồng: Baseline Linear/Ridge + RF/XGBRegressor.\par
MAE/RMSE.\par
\emph{Chuỗi thời gian}: split theo năm, đánh giá drift/seasonality. \\
\hline

8. Phát hiện gian lận &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud}{Credit Card Fraud}} &
Rời rạc hoá (amount/time bins).\par
Tìm pattern thường gặp ở fraud.\par
Top luật + lift (chỉ dùng như insight/feature). &
Phân cụm/anomaly cluster (HDBSCAN/K-means).\par
Chuẩn hoá.\par
Đánh giá, mô tả cụm bất thường. &
Phân lớp fraud/legit.\par
Imbalance mạnh.\par
PR-AUC + chọn ngưỡng theo chi phí sai.\par
Phân tích false positive/negative. &
Semi-supervised anomaly + thiếu nhãn.\par
Giả lập ít nhãn fraud, self-training hoặc one-class/PU-learning (mức cơ bản), learning curve, phân tích rủi ro pseudo-label. &
\emph{Không yêu cầu sử dụng hồi quy và chuỗi thời gian} \\
\hline

9. Phân tích chất lượng nước &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/adityakadiwal/water-potability}{Water quality datasets}} &
Rời rạc hoá chỉ số ô nhiễm.\par
Apriori tìm chỉ số hay cùng tăng.\par
Top luật + diễn giải theo ngưỡng an toàn. &
Phân cụm nguồn nước theo profile.\par
Chuẩn hoá.\par
Chọn K.\par
Profiling cụm + cảnh báo vùng rủi ro. &
Phân lớp an toàn/không an toàn (nếu có nhãn/chuẩn).\par
F1/PR-AUC + phân tích lỗi gần ngưỡng. &
Giả lập ít nhãn, label spreading k-NN graph, learning curve, phân tích pseudo-label sai ở vùng ít mẫu. &
Dự báo WQI hoặc chỉ số liên tục.\par
MAE/RMSE.\par
Dự báo các chỉ số chất lượng nước.\\
\hline

10. Dự báo nhu cầu năng lượng &
UCI: \textcolor{blue}{\href{https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption}{Household Power Consumption}} &
Nếu có thiết bị: basket thiết bị dùng cùng.\par
Nếu không: rời rạc hoá trạng thái (peak/off-peak) rồi Apriori tìm đồng xuất hiện điều kiện. &
Phân cụm hộ theo profile tiêu thụ.\par
Chuẩn hoá.\par
Phân cụm và Profiling (night-owl, peak-heavy...). &
\emph{Không áp dụng học bán giám sát}\par
F1 + phân tích lỗi theo mùa. &
\emph{Không áp dụng hồi quy} \par
Nhánh thay thế: anomaly mining (phát hiện ngày bất thường) kèm đánh giá. &
Dự báo nhu cầu năng lượng \par
Split theo thời gian.\par
Baseline seasonal-naive.\par
ARIMA/ETS/Holt-Winters.\par
MAE/RMSE/sMAPE + residual + outlier. \\
\hline

11. Phân tích đánh giá khách sạn \& chủ đề dịch vụ &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/datafiniti/hotel-reviews}{Hotel reviews datasets}} &
Phân tích luật kết hợp trên từ khoá/khía cạnh (aspect) sau khi rời rạc hoá.\par
Top luật dịch vụ đi kèm phàn nàn/khen. &
Vector hoá.\par
Phân cụm chủ đề (topic clusters).\par
Đặt tên cụm + review đại diện.\par &
Phân lớp sentiment/aspect.\par
F1-macro + phân tích lỗi review đa chủ đề. &
Thiếu nhãn aspect/sentiment theo domain.\par
Giả lập ít nhãn, label spreading/self-training, learning curve, phân tích pseudo-label sai ở review ngắn. &
Hồi quy rating.\par
MAE/RMSE.\par
\emph{Không yêu cầu áp dụng chuỗi thời gian} \\
\hline

12. Dự đoán huỷ đặt phòng &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand}{Hotel Booking Demand dataset}} &
Rời rạc hoá lead time/channel/country.\par
Luật kết hợp tìm combo thuộc tính liên quan huỷ.\par
So sánh theo mùa/quốc gia. &
Phân cụm booking theo hành vi.\par
Chuẩn hoá.\par
Profiling cụm rủi ro huỷ cao. &
Phân lớp huỷ/không huỷ.\par
Imbalance.\par
PR-AUC/F1.\par
Kiểm tra leakage (thông tin sau đặt phòng). &
Giả lập ít nhãn, self-training ngưỡng cao, learning curve, phân tích pseudo-label sai theo lead time dài. &
\emph{Không yêu cầu áp dụng hồi quy.}\par
MAE/RMSE.\par
Chuỗi thời gian dự báo cancellation rate theo tháng. \\
\hline

13. Dự đoán trả hàng TMĐT &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/carrie1/ecommerce-data}{E-commerce returns datasets}} &
Rời rạc hoá category/shipping/promo.\par
Luật kết hợp tìm combo liên quan trả hàng.\par
Top luật + insight chính sách đổi trả. &
Phân cụm khách/sản phẩm theo return rate.\par
Chuẩn hoá.\par
Profiling cụm rủi ro trả cao. &
Phân lớp return/no-return.\par
Imbalance.\par
PR-AUC.\par
Phân tích lỗi theo category. &
Nhãn trả hàng có thể thiếu/đến muộn.\par
Giả lập ít nhãn, self-training, learning curve, phân tích pseudo-label sai do promo/season. &
\emph{Không yêu cầu áp dụng hồi quy.}\par
Chuỗi thời gian dự báo return rate theo tuần/tháng. \\
\hline

14. Dự báo giá/biến động crypto &
Kaggle: \textcolor{blue}{\href{https://www.kaggle.com/datasets/sudalairajkumar/cryptocurrencypricehistory}{Cryptocurrency Historical Prices dataset}} &
Rời rạc hoá trạng thái (up/down/high-vol bins).\par
Luật kết hợp tìm coin biến động cùng.\par
Top luật + so sánh theo regime. &
Phân cụm coin theo volatility/return/indicators.\par
Chuẩn hoá.\par
Profiling cụm (majors/high-risk...). &
\emph{Tuỳ chọn}: phân lớp trend up/down.\par
ROC-AUC/F1 + phân tích lỗi khi tin tức sốc. &
\emph{Không yêu cầu áp dụng học bán giám sát} &
Chuỗi thời gian dự báo price/return.\par
Split theo thời gian, walk-forward.\par
Baseline naive.\par
ARIMA/ETS.\par
MAE/RMSE + residual + volatility regime. \\
\hline

15. Phân nhóm học tập \& dự đoán trượt môn &
UCI: \textcolor{blue}{\href{https://archive.ics.uci.edu/dataset/320/student+performance}{Student Performance}}&
Rời rạc hoá hành vi (activity bins).\par
Apriori tìm pattern hành vi đi kèm trượt/đỗ.\par
Top luật + gợi ý can thiệp sớm. &
Phân cụm sinh viên theo hành vi.\par
Chuẩn hoá.\par
Chọn K.\par
Profiling cụm + khuyến nghị học tập. &
Phân lớp pass/fail.\par
PR-AUC/F1.\par
Phân tích lỗi theo tuần học/nhóm yếu. &
\emph{Rất phù hợp}: nhãn kết quả chỉ có cuối kỳ, thiếu nhãn sớm.\par
Giả lập ít nhãn, label spreading/self-training, learning curve, phân tích pseudo-label sai ở tuần đầu. &
\emph{Phù hợp (chuỗi thời gian)} với OULAD (theo tuần).\par
Dự báo điểm/engagement theo tuần: split theo thời gian, baseline, ARIMA/ETS (hoặc mô hình đơn giản), MAE/sMAPE. \\
\hline

16. Phân tích lỗi sản xuất \& dự đoán lỗi &
UCI: \textcolor{blue}{\href{https://archive.ics.uci.edu/dataset/601/ai4i+2020+predictive+maintenance+dataset}{AI4I 2020 Predictive Maintenance}} &
Rời rạc hoá trạng thái máy (bin sensor/setting).\par
Apriori tìm combo điều kiện liên quan lỗi.\par
Top luật + insight vận hành. &
Phân cụm máy/chu kỳ theo hành vi.\par
Chuẩn hoá.\par
Profiling cụm + lịch bảo trì. &
Phân lớp lỗi/không lỗi (hoặc loại lỗi).\par
Imbalance.\par
PR-AUC/F1.\par
Phân tích lỗi theo loại lỗi. &
Áp dụng trong trường hợp nhãn lỗi hiếm/khó gán.\par
Giả lập ít nhãn, self-training ngưỡng cao, learning curve, phân tích rủi ro pseudo-label (false alarm). &
Sử dụng mô hình hồi quy dự đoán biến liên tục như \texttt{Tool wear [min]} (hoặc tự tạo \texttt{RUL/time-to-failure} từ \texttt{Machine failure}).
MAE/RMSE.\par
Dataset không có timestamp, chỉ có \texttt{UID} theo thứ tự; coi như time index để ARIMA/lag-features khi chấp nhận giả định “UID $\approx$ thời gian”. \par
Chia train/test theo thứ tự quan sát (không shuffle), đánh giá MAE/RMSE.\\
\hline


\caption{Danh sách đề tài bài tập lớn}
\label{subject}
\end{longtable}

\normalsize
\restoregeometry
\endgroup
```

# Rubic chấm điểm 

\begin{longtable}{|
  >{\raggedright\arraybackslash}p{0.28\linewidth}|
  >{\centering\arraybackslash}p{0.10\linewidth}|
  >{\raggedright\arraybackslash}p{0.54\linewidth}|
}
\hline
\textbf{Tiêu chí} & \textbf{Điểm tối đa} & \textbf{Đánh giá (Đạt / Trung bình / Chưa đạt)} \\
\hline
\endfirsthead

\hline
\textbf{Tiêu chí} & \textbf{Điểm tối đa} & \textbf{Đánh giá (Đạt / Trung bình / Chưa đạt)} \\
\hline
\endhead

A. Bài toán + mô tả dữ liệu + data dictionary & 1.0 &
Đạt: Mục tiêu rõ ràng; mô tả nguồn dữ liệu; giải thích cột/nhãn/target; có data dictionary; nêu rủi ro như mất cân bằng lớp, thiếu dữ liệu, data leakage (nếu có).\par
Trung bình: Có mô tả nhưng thiếu 1--2 ý quan trọng (ví dụ thiếu data dictionary hoặc chưa nói về leakage/imbalance).\par
Chưa đạt: Mơ hồ; thiếu nguồn dữ liệu; không nêu target/label hoặc không giải thích dữ liệu. \\
\hline

B. EDA \& tiền xử lý & 1.5 &
Đạt: EDA có ít nhất 3 biểu đồ kèm diễn giải; xử lý missing/outlier/duplicate; encoding/scaling hợp lý; có thống kê trước--sau hoặc pipeline hoá.\par
Trung bình: Có EDA và tiền xử lý nhưng phân tích còn nông; thiếu kiểm soát tham số hoặc thiếu thống kê trước--sau.\par
Chưa đạt: EDA sơ sài hoặc chỉ chụp hình; tiền xử lý tuỳ tiện hoặc sai. \\
\hline

C. Data Mining core (pattern/cluster/anomaly/rule/graph) & 2.0 &
Đạt: Có ``khai phá tri thức'' đúng chất (phân cụm/pattern/anomaly/rule/graph); trình bày tham số; có đánh giá (silhouette/DBI/coverage/runtime...); rút insight rõ ràng.\par
Trung bình: Có mining nhưng hời hợt; thiếu đánh giá hoặc thiếu diễn giải kết quả.\par
Chưa đạt: Không có phần mining; chỉ huấn luyện mô hình dự đoán. \\
\hline

D. Mô hình hoá + baseline so sánh (>= 2 baseline) & 2.0 &
Đạt: Có ít nhất 2 baseline và 1 mô hình cải tiến; giải thích lựa chọn; có so sánh rõ ràng.\par
Trung bình: Có baseline nhưng chưa rõ vai trò/thiết lập; thiếu so sánh hoặc mô hình cải tiến chưa thuyết phục.\par
Chưa đạt: Chỉ 1 mô hình hoặc không có so sánh baseline. \\
\hline

E. Thiết kế thực nghiệm + metric đúng & 1.0 &
Đạt: Split/CV hợp lý; đặt seed; tránh leakage; chọn metric phù hợp (F1/PR-AUC/ROC-AUC; RMSE/MAE/sMAPE; silhouette/DBI...).\par
Trung bình: Có thực nghiệm nhưng thiếu kiểm soát (seed/leakage); metric đúng nhưng giải thích chưa rõ.\par
Chưa đạt: Thiết kế thực nghiệm sai; metric không phù hợp hoặc không nêu rõ. \\
\hline

F. Bán giám sát hoặc nhánh thay thế tương đương & 1.0 &
Đạt: \emph{Nếu đề tài phân lớp:} có kịch bản thiếu nhãn (10--30\% labeled), so sánh supervised-only vs semi-supervised (self-training/label spreading), có learning curve theo \% nhãn và phân tích pseudo-label sai.\par
Trung bình: Có triển khai nhưng thiếu một phần (thiếu learning curve/thiếu phân tích lỗi/thiếu so sánh).\par
Chưa đạt: Không thực hiện semi-supervised (khi bắt buộc) hoặc không có nhánh thay thế (khi không áp dụng). \\
\hline

G. Đánh giá, phân tích lỗi \& insight hành động & 1.5 &
Đạt: Có phân tích lỗi (confusion matrix/residual); nêu dạng sai phổ biến; có ít nhất 5 insight ``có hành động'' (actionable) gắn với kết quả.\par
Trung bình: Có insight nhưng chung chung; phân tích lỗi còn nông.\par
Chưa đạt: Không phân tích lỗi; insight mơ hồ hoặc không có khuyến nghị. \\
\hline

H. Repo GitHub chuẩn + chạy lại được (reproducible) & 1.0 &
Đạt: Repo đúng cấu trúc; có README, requirements/environment; có configs/outputs; chạy lại tạo ra kết quả; notebook ``sạch'' (gọi code từ src).\par
Trung bình: Repo tương đối ổn nhưng thiếu 1--2 phần (ví dụ thiếu script chạy pipeline hoặc thiếu hướng dẫn); vẫn còn nhiều code trong notebook.\par
Chưa đạt: Repo lộn xộn; thiếu hướng dẫn; không chạy lại được. \\
\hline

\caption{Thang đánh giá đề tài bài tập lớn}
\label{table:rubric_10_points_3cols}
\end{longtable}

