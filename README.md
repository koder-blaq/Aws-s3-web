# Development & Deployment of a Static Website Using HTML, Internal CSS & AWS S3

Author: Ridwan Olasunkanmi Mudashiru
Reg. No: AWS/2025/TC4/008
Date: December 2025

## Introduction

This project focuses on building a simple static website using HTML and internal CSS, and deploying it to the cloud using Amazon S3. The aim is to give beginners practical experience with:

i. Basic web development

ii. Git version control

iii. Cloud hosting

iv. Static website deployment

This mirrors the foundational workflow used in DevOps: Build → Version → Deploy.

## Project Objectives
i. Create a basic static webpage using HTML and internal CSS.

ii. Understand folder structure and how static websites work.

iii. Use Git commands to initialize a repository, commit changes, and push to GitHub.

iv. Deploy the static website on AWS S3 with public access.

v. Learn how cloud storage works for hosting websites.

vi. Troubleshoot errors during Git push and AWS configuration.

## Project Requirements

Technologies Used:
HTML5, Internal CSS, Git, GitHub, AWS S3, AWS Console, Web browser (Chrome/Edge)

Prerequisites:
Active AWS account, Git installed, Stable internet connection

## Development Process
Step 1 — Creating the HTML Structure
- File: index.html

Step 2 — Adding Internal CSS
- Styling is included in the <style> tag inside index.html.

Version Control (Git Workflow)
[
    
    {
    git init
    git add .
    git commit -m "Initial commit"
    git branch -M main
    git remote add origin https://github.com/koder-blaq/Aws-s3-Web.git
    git push -u origin main
    }
]

## Deployment on AWS S3
Step 1 — Create S3 Bucket
  - Log in to AWS → S3 → Create Bucket
  - Enter unique name, uncheck Block all public access, and create.

Step 2 — Upload Website Files
  - Upload index.html to the bucket.

Step 3 — Enable Static Website Hosting
  - Properties → Static website hosting → Enable
  - Set index.html as the index document
  - Copy the URL to access your site.

Step 4 — Add Public Access Policy

{
  "Version": "2012-10-17",
  "Statement": [
  
      {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}

Replace your-bucket-name with your actual S3 bucket name.

## Problems Encountered & Solutions

i. src refspec main does not match any

- Cause: Git repo not initialized or no commit
- Solution: Initialize Git, add files, commit, and rename branch to main

ii. Website not loading on S3

- Cause: Public access blocked
- Solution: Disabled block and added bucket policy

iii. Incorrect file name

- Cause: Case-sensitive S3 file naming
- Solution: Rename to index.html (all lowercase)

iv. file not found in S3

- cause: folder was uploaded instead of the index file itself
- Solution: delete the uploaded folder and re-upload the index.html file only. 
