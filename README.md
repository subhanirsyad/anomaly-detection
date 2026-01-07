# Anomaly Detection — Event Log (Isolation Forest + SHAP)

Proyek ini melakukan **deteksi anomali** pada data **event log** (format JSON Lines: 1 event per baris).
Model utama yang digunakan adalah **Isolation Forest**, lalu hasilnya dijelaskan dengan **SHAP** untuk interpretasi fitur.

📓 Notebook: [`notebooks/anomaly_detection.ipynb`](./notebooks/anomaly_detection.ipynb)  
📄 Makalah/Laporan: [`report/paper.pdf`](./report/paper.pdf)

---

## Dataset
Notebook mengasumsikan dataset berupa **JSON Lines** (kadang berekstensi `.json` tapi isinya JSONL), dengan minimal field:
- `uid`  : id user
- `time` : timestamp ISO (contoh: `2020-01-01T12:34:56Z`)
- `type` : tipe event (mis: `login`, `file_accessed`, dll)



---

## Metodologi (ringkas)
- Parsing & normalisasi field event (`uid`, `time`, `type`)
- Feature engineering dari aktivitas (agregasi per user/per waktu)
- Model: **Isolation Forest**
- Interpretasi: **SHAP (TreeExplainer)**

---

## Tools / Library
`pandas`, `numpy`, `scikit-learn`, `shap`, `matplotlib`

---

## Struktur Folder
```
anomaly-detection/
  notebooks/
  report/
  data/        # tempat dataset (tidak disertakan)
  src/         # opsional (kalau mau pisahkan fungsi dari notebook)
```
