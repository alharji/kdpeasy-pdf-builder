# 📄 KDPEasy PDF Builder

Tool #2 in the **KDPEasy Suite** — combine 30–100 images into a single
print-ready PDF for Amazon KDP, with the right page size, DPI, and fit
mode. Free gift for our VIP email subscribers.

**Live app:** https://kdpeasy-pdf-builder.streamlit.app

---

## 🇻🇳 Hướng dẫn deploy (dành cho anh chủ tool)

Anh làm đúng 3 bước này — không cần Git, không cần terminal.

### Bước 1 — Tạo repo mới trên GitHub
1. Mở https://github.com/new
2. **Repository name:** `kdpeasy-pdf-builder`
3. **Public** ✅
4. ✅ Tick "Add a README file"
5. Bấm **Create repository**

### Bước 2 — Upload 3 file vào repo
Trong repo vừa tạo, bấm nút **Add file → Upload files**, kéo cả 3 file
trong thư mục `C:\Users\Admin\Downloads\KDPEasy-PDF-Builder\` lên:

- `app.py`
- `requirements.txt`
- `README.md` (file này — sẽ ghi đè cái GitHub tự tạo)

Bấm **Commit changes**.

### Bước 3 — Deploy lên Streamlit Cloud
1. Mở https://share.streamlit.io
2. Bấm **New app**
3. Chọn repo `daodinhthe1989-blip/kdpeasy-pdf-builder`
4. **Branch:** `main` — **Main file path:** `app.py`
5. **App URL** (tùy chọn): để mặc định hoặc đặt `kdpeasy-pdf-builder`
6. Bấm **Deploy**

Đợi ~2 phút là app chạy. Mật khẩu vào tool: **`KDPPDF2026`**

> 💡 Tool #2 **không cần** Replicate API token — toàn bộ xử lý ảnh chạy
> ngay trên server Streamlit miễn phí.

### Đổi mật khẩu sau này
Mở `app.py` trên GitHub → bấm icon ✏️ (Edit) → sửa dòng:

```python
APP_PASSWORD = "KDPPDF2026"
```

→ bấm **Commit changes**. Streamlit tự deploy lại trong 1–2 phút.

---

## 🇺🇸 How to use (for customers)

### What this tool does
Turns a folder of images (coloring book pages, art prints, photo book
spreads…) into one print-ready PDF that you can upload straight to
Amazon KDP.

### Step-by-step
1. **Unlock** with the VIP password from your welcome email.
2. **Pick a page size** in the left sidebar (6×9 in is the KDP default
   for coloring books).
3. **Choose a fit mode:**
   - **Fit** — keeps the whole image, may leave a white margin.
   - **Fill** — covers the page edge-to-edge, may crop a little.
   - **Center** — places the image at its real size in the middle.
4. **Upload your images.** Drag and drop up to 200 files at once.
   PNG, JPG, WEBP, and TIFF are supported.
5. **Reorder** with the ⬆️ ⬇️ buttons or by typing a new position
   number. ❌ removes a page from the PDF.
6. **Check the quality column.** Any image marked ⚠️ or ❌ is below
   300 DPI at your chosen page size — upscale it first with the
   [KDPEasy AI Upscaler](https://kdpeasy-upscaler.streamlit.app)
   for crisp KDP print.
7. **Click "Build PDF"** and download.

### Recommended settings for coloring books
- Page size: **8.5 × 11 in (Letter)** or **8 × 10 in**
- Fit mode: **Fit** (keeps the full coloring page visible)
- DPI: **300**
- JPEG quality: **92**
- Background: **white** (#FFFFFF)

### File size tips
- 100 pages at 300 DPI / quality 92 → about 30–80 MB.
- KDP accepts PDFs up to 650 MB.
- Lower the **JPEG quality** slider to 85 if your file is too large.

---

## 🛠️ Tech stack
- **Streamlit** — UI
- **Pillow** — image compositing, fit modes, DPI handling
- **img2pdf** — lossless image → PDF assembly

No paid APIs. Runs free on Streamlit Cloud.

---

Made with ❤️ by **KDPEasy Studio** for our VIP customers.
