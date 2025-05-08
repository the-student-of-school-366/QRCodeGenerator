# 📦 QR Code Generator with Optional PNG Watermark

A minimalistic HTTP microservice written in Go that generates QR codes with optional PNG watermark overlays. Upload a watermark image, specify the content and size, and receive a ready-to-use PNG QR code.

## 🚀 Features

- ✅ Generate high-quality QR codes via `POST /generate`
- ✅ Optional PNG watermark overlay centered on the QR code
- ✅ Fully HTTP-based (no CLI or UI needed)
- ✅ Fast, stateless and easy to deploy

---

## 📸 Example

**Request:**  
POST `http://localhost:8083/generate`  
Content-Type: `multipart/form-data`

**Form Data:**

| Key        | Type  | Required | Description                             |
|------------|-------|----------|-----------------------------------------|
| `size`     | Text  | ✅       | QR code image size in pixels (e.g. 256) |
| `content`  | Text  | ✅       | URL or text to encode                   |
| `watermark`| File  | ❌       | Optional `.png` file for watermark      |

**Response:**  
Returns `image/png` with the generated QR code. Returns `400 Bad Request` on error.

---

## 🛠️ Setup & Run

### Prerequisites
- Go 1.18 or newer

### Clone and run

```bash
git clone https://github.com/yourusername/qrcode-generator-go.git
cd qrcode-generator-go
go run main.go
