# 🌤 Cloud Image Upload Demo

This project demonstrates how to upload an image to Amazon S3 and render it in a static HTML page. It includes cloud configuration, public access setup, Postman testing, and basic security enhancements.

---

## Project Overview

- **Cloud Provider:** Amazon Web Services (S3)
- **Frontend:** Static HTML
- **Tools Used:** AWS Console, Postman
- **Security Features:** CORS configuration, Content Security Policy (CSP)

---

## How to Run Locally

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/cloud-image-upload.git
   cd cloud-image-upload
   ```
2. Open index.html in your browser.
3. Confirm the image loads from the cloud.

---

## Postman Test

A successful GET request was made to the image URL using Postman.

---

## Security Enhancements

**CORS:** Configured to allow requests only from trusted domains.
**CSP:** Added to HTML to restrict image sources:
```html
<meta http-equiv="Content-Security-Policy" content="default-src 'self'; img-src https://your-bucket-name.s3.amazonaws.com;">
```

---

## File Structure

```code
cloud-image-upload/
├── index.html
├── README.md
├── docs/
│   └── setup_instructions.md
├── screenshots/
│       ├── Bucket Creation.png
│       ├── Postman_test.png
│       └── index.html.png
```
