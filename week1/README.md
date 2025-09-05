# SWENG 861 – Week 1 Assignment  
**Git Usage & Cloud Image Upload**

This repository contains two hands-on projects demonstrating Git collaboration workflows and cloud-based image hosting with HTML integration. Both assignments simulate real-world scenarios and emphasize reproducibility, version control, and secure web development practices.

---

## Assignment 1: Git Usage

Simulates two users (User1 and User2) collaborating on a shared GitHub repository. Each user clones the repo, creates and edits files, commits changes, and merges branches.

### Workflow Summary

- Created `development` branch from `main`
- User1 added `myinfo.txt` and `dev1.txt`
- User2 added `dev2.txt` and edited `myinfo.txt`
- Multiple merges from `development` into `main`
- Final file structure for Git Usage:
```code
week1/
├── myinfo.txt
├── dev1.txt
├── dev2.txt
├── git-usage-screenshots/
│       ├── network_graph.png
│       ├── Git_revision_history.png
│       └── Final_commit_ID.png
└── cloud-image-upload/ [for next assignment]
```

---

## Assignment 2: Cloud Image Upload

Demonstrates how to upload an image to Amazon S3 and render it in a static HTML page. Includes public access configuration, Postman testing, and basic security enhancements.

### Workflow Summary

- Created S3 bucket and uploaded `cloud-demo.jpg`
- Configured public access via bucket policy
- Rendered image in `index.html` using HTTPS
- Verified image accessibility via Postman
- Implemented security features:
- CORS configuration to restrict access
- Content Security Policy (CSP) in HTML

### File Structure
```code
week1/cloud-image-upload/
├── index.html
├── README.md
├── setup_instructions.md
├── screenshots/
│       ├── Bucket Creation.png
│       ├── Postman_test.png
│       └── index.html.png
```

---

## Security Highlights

- CORS: Configured to allow only trusted origins
- CSP: Restricted image sources via meta tag
- HTTPS: Used secure URLs for image loading

---

## Author

**Chastidy Joanem**  

