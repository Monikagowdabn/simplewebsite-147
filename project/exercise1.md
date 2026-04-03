# Exercise 1: Create Your S3 Buckets

## What You Will Do
In this exercise, you will create three S3 buckets — a source bucket, a destination bucket, and a website bucket.

---

## Task 1: Create the Source Bucket

1. Go to **AWS Management Console** → search for **S3** → click **S3**
2. Click **Create bucket**
3. Enter the following details:
   - **Bucket name:** `source-bucket-yourname` *(replace yourname with your name)*
   - **Region:** Select your preferred region *(e.g. eu-north-1)*
4. Under **Block Public Access settings**, leave all options **checked** (keep it private)
5. Scroll down to **Bucket Versioning** → click **Enable**
6. Click **Create bucket**

✅ Your source bucket is created.

---

## Task 2: Create the Destination Bucket

1. Click **Create bucket**
2. Enter the following details:
   - **Bucket name:** `destination-bucket-yourname`
   - **Region:** Select a **different region** from the source bucket *(e.g. eu-west-1)*
3. Under **Block Public Access settings**, leave all options **checked** (keep it private)
4. Scroll down to **Bucket Versioning** → click **Enable**
5. Click **Create bucket**

✅ Your destination bucket is created.

---

## Task 3: Create the Website Bucket

1. Click **Create bucket**
2. Enter the following details:
   - **Bucket name:** `website-bucket-yourname`
   - **Region:** Select any region
3. Under **Block Public Access settings**:
   - **Uncheck** all options
   - Check the acknowledgement box that appears
4. Scroll down to **Bucket Versioning** → click **Enable**
5. Click **Create bucket**

✅ Your website bucket is created.

---

## Verify

1. On the S3 console, confirm you can see all three buckets:
   - `source-bucket-yourname`
   - `destination-bucket-yourname`
   - `website-bucket-yourname`
2. Click each bucket → go to **Properties** tab → confirm **Versioning** shows **Enabled**

---

You are now ready for **Exercise 2: Set Up Bucket Policies**
