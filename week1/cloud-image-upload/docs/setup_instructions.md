
# Cloud Image Upload — Setup Instructions

This guide outlines the steps taken to upload an image to Amazon S3 and display it in a static HTML page. It also includes Postman testing and basic security enhancements.

---

## 🪣 Step 1: Create an S3 Bucket

1. Log in to the AWS Management Console.
2. Navigate to **S3** and click **Create bucket**.
3. Name your bucket (e.g., `chastidy-image-bucket`) and choose a region.
4. Disable "Block all public access" to allow public image viewing.
5. Complete the setup and create the bucket.

---

## 📤 Step 2: Upload an Image

1. Open your bucket and click **Upload**.
2. Select an image file (e.g., `cloud-demo.jpg`) and upload it.
3. After upload, click the image and copy its **Object URL**: "https://chastidy-image-bucket.s3.us-east-2.amazonaws.com/myphoto.jpg"


---

## 🔓 Step 3: Configure Public Access

1. In the image’s **Permissions** tab, set the object to public.
2. Alternatively, apply a bucket policy to allow public read access:
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::cloud-image-demo/*"
    }
  ]
}
```

---

## 🌐 Step 4: Create index.html

1. Create a simple HTML file to display the image

```html
<!DOCTYPE html>
<html>
  <head><title>Image Test</title></head>
  <body>
    <h1>My Cloud Image</h1>
    <img src="https://chastidy-image-bucket.s3.us-east-2.amazonaws.com/myphoto.jpg" alt="Uploaded Image" />
  </body>
</html>
```

---

## 🧪 Step 5: Test with Postman

1. Open Postman and create a GET request to the image URL.
2. Click Send and verify the image loads in the response preview.
3. Save a screenshot for documentation.

---

## 🛡️ Step 6: Security Enhancements
### CORS Configuration
To restrict access to trusted domains:

1. Go to the bucket → Permissions → CORS configuration.
2. Add:
```xml
<CORSConfiguration>
  <CORSRule>
    <AllowedOrigin>https://yourdomain.com</AllowedOrigin>
    <AllowedMethod>GET</AllowedMethod>
    <AllowedHeader>*</AllowedHeader>
  </CORSRule>
</CORSConfiguration>
```

### Content Security Policy (CSP)
1. Added to index.html to prevent unauthorized image sources:

```html
<meta http-equiv="Content-Security-Policy" content="default-src 'self'; img-src https
```
