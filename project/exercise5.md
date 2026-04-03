# Exercise 5: Host a Static Website

## What You Will Do
In this exercise, you will turn your website bucket into a publicly accessible static website and upload your website files.

---

## Task 1: Prepare Your Website Files

Before configuring the bucket, create two simple HTML files on your computer.

**index.html** — copy and save this as `index.html`:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My S3 Website</title>
  </head>
  <body>
    <h1>Welcome to My S3 Website!</h1>
    <p>This website is hosted on Amazon S3.</p>
  </body>
</html>
```

**error.html** — copy and save this as `error.html`:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Error</title>
  </head>
  <body>
    <h1>404 - Page Not Found</h1>
    <p>The page you are looking for does not exist.</p>
  </body>
</html>
```

---

## Task 2: Enable Static Website Hosting

1. Go to **S3** → click on your **website bucket**
2. Click the **Properties** tab
3. Scroll down to **Static website hosting** → click **Edit**
4. Select **Enable**
5. Under **Hosting type**, select **Host a static website**
6. Enter the following:
   - **Index document:** `index.html`
   - **Error document:** `error.html`
7. Click **Save changes**

✅ Static website hosting enabled.

---

## Task 3: Upload Your Website Files

1. Go to your **website bucket** → click the **Objects** tab
2. Click **Upload**
3. Click **Add files**
4. Select both `index.html` and `error.html` from your computer
5. Click **Upload**
6. Click **Close** once upload is complete

✅ Website files uploaded.

---

## Task 4: Get Your Website URL

1. Go to your **website bucket** → click the **Properties** tab
2. Scroll down to **Static website hosting**
3. Copy the **Bucket website endpoint** URL shown at the bottom

It will look something like:
```
http://website-bucket-yourname.s3-website-eu-north-1.amazonaws.com
```

---

## Task 5: Open Your Website

1. Paste the URL in your browser
2. You should see your webpage with the message **"Welcome to My S3 Website!"**

✅ Your website is live!

---

## Verify

1. Open the website URL — confirm `index.html` loads correctly
2. Add `/anything` to the URL — confirm `error.html` loads showing the 404 message
3. Go to **website bucket** → **Objects** tab — confirm both files are listed

---

You have completed all exercises! Head over to the **Summary** to review what you built.
