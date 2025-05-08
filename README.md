# 📦 QRCodeGenerator

A lightweight Go HTTP microservice that generates QR codes with optional PNG watermark overlays. Just provide content and size via a POST request — and optionally attach a watermark image — and the server returns a high-quality PNG QR code.

---

## 🚀 Features

- ✅ Generate QR codes via `POST /generate`
- ✅ Optional PNG watermark overlay, centered on the QR code
- ✅ Fully HTTP-based, easy to integrate into any system
- ✅ Simple deployment, no dependencies beyond Go

---

## 📸 Example Usage

**Endpoint:**  
`POST http://localhost:8083/generate`  
`Content-Type: multipart/form-data`

### Form Fields

| Key        | Type  | Required | Description                             |
|------------|-------|----------|-----------------------------------------|
| `size`     | Text  | ✅       | QR code image size in pixels (e.g. 256) |
| `content`  | Text  | ✅       | The string or URL to encode             |
| `watermark`| File  | ❌       | Optional `.png` watermark overlay       |

### Sample Response

- Returns a `Content-Type: image/png` QR code.
- On error, returns `400 Bad Request` with a JSON message.

---

## 🛠️ Setup & Run Locally

### Prerequisites

- Go 1.18 or newer

### Clone and Run

```bash
git clone https://github.com/the-student-of-school-366/QRCodeGenerator.git
cd QRCodeGenerator
go run main.go
