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
http://website-bucket-{DeploymentID}.s3-website-us-east-1.amazonaws.com
```

<img width="1907" height="838" alt="image" src="https://github.com/user-attachments/assets/a0fbc8d3-d599-48f5-a996-3bd52282e870" />

---

## Task 2: Verify Website Files in the Bucket

1. Go to **S3** → click on **`website-bucket-{DeploymentID}`**

2. Click the **Objects** tab

3. Confirm both files are present:

   - **`index.html`** ✅

   - **`error.html`** ✅

> These files were automatically uploaded by the Lambda function (`WebsiteFileUploaderFunction`) during stack deployment.

<img width="1918" height="746" alt="image" src="https://github.com/user-attachments/assets/fbab94bc-29ec-4f44-ad33-1157b3428b3b" />

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

<img width="1895" height="953" alt="image" src="https://github.com/user-attachments/assets/5e682cd3-9efd-4d42-8e31-2da7dee06667" />

<img width="1261" height="859" alt="image" src="https://github.com/user-attachments/assets/fc83e970-9d0b-4135-8af4-53bc8f5d75c3" />

<img width="1896" height="940" alt="image" src="https://github.com/user-attachments/assets/1a6748a5-bedf-433d-8718-1bfca9830edc" />

<img width="1882" height="922" alt="image" src="https://github.com/user-attachments/assets/16085dbf-5cf9-4763-83f6-939da703d33e" />

---

## Task 4: Test the Error Page

1. Take the website URL and add `/anything` at the end:

   ```
   http://website-bucket-{DeploymentID}.s3-website-us-east-1.amazonaws.com/anything
   ```

2. You should see the **404 error page** load with the message **"Getting Lost is Part of the Journey"** ✅

<img width="1905" height="956" alt="image" src="https://github.com/user-attachments/assets/6445a840-e894-4918-a139-522f92b1b812" />

---

## Task 5: Verify Static Website Hosting Settings

1. Go to **S3** → click on **`website-bucket-{DeploymentID}`**

2. Click the **Properties** tab

3. Scroll down to **Static website hosting**

4. Confirm:

   - **Static website hosting:** Enabled ✅

   - **Index document:** `index.html` ✅

   - **Error document:** `error.html` ✅

   - **Bucket website endpoint:** matches your `WebsiteURL` from CloudFormation Outputs ✅

<img width="1865" height="835" alt="image" src="https://github.com/user-attachments/assets/33728101-fba2-4845-a3e1-2a279a0f6591" />

---

## Verify

| Check | Status |
|-------|--------|
| `index.html` present in `website-bucket-{DeploymentID}` | ✅ |
| `error.html` present in `website-bucket-{DeploymentID}` | ✅ |
| Website URL opens Vision Board page | ✅ |
| Wrong URL shows 404 error page | ✅ |
| Static website hosting enabled on bucket | ✅ |

---

You have completed all exercises! Head over to the **Summary** to review what was built.
