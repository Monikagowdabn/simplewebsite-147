# Exercise 5: View Your Static Website

## What You Will Do
In this exercise, you will get the website URL from CloudFormation Outputs and open your live static website that was automatically deployed by the Lambda function.

---

## Task 1: Get the Website URL from CloudFormation

1. Go to **AWS Management Console** → search for **CloudFormation** → click **CloudFormation**
2. Click on your stack name
3. Click the **Outputs** tab
4. Find the key **`WebsiteURL`**
5. Copy the URL value — it will look like:
```
http://s3auto-dev-websitebucket.s3-website-us-east-1.amazonaws.com
```

---

## Task 2: Verify Website Files in the Bucket

1. Go to **S3** → click on **`s3auto-dev-websitebucket`**
2. Click the **Objects** tab
3. Confirm both files are present:
   - **`index.html`** ✅
   - **`error.html`** ✅

> These files were automatically uploaded by the Lambda function during stack deployment.

---

## Task 3: Open Your Website

1. Paste the **WebsiteURL** you copied in Task 1 into your browser
2. You should see the **Vision Board** website load successfully ✅
3. The page should display:
   - A hero section with **"Dream Big. Start Today."**
   - Vision board image grid
   - Motivational quotes
   - Daily affirmations
   - Goals roadmap

---

## Task 4: Test the Error Page

1. Take the website URL and add `/anything` at the end
   ```
   http://s3auto-dev-websitebucket.s3-website-us-east-1.amazonaws.com/anything
   ```
2. You should see the **404 error page** load with the message **"Getting Lost is Part of the Journey"** ✅

---

## Task 5: Verify Static Website Hosting Settings

1. Go to **S3** → click on **`s3auto-dev-websitebucket`**
2. Click the **Properties** tab
3. Scroll down to **Static website hosting**
4. Confirm:
   - **Static website hosting:** Enabled ✅
   - **Index document:** `index.html` ✅
   - **Error document:** `error.html` ✅
   - **Bucket website endpoint:** matches your WebsiteURL ✅

---

## Verify

| Check | Status |
|-------|--------|
| `index.html` present in website bucket | ✅ |
| `error.html` present in website bucket | ✅ |
| Website URL opens Vision Board page | ✅ |
| Wrong URL shows 404 error page | ✅ |
| Static website hosting enabled on bucket | ✅ |

---

You have completed all exercises! Head over to the **Summary** to review what was built.
