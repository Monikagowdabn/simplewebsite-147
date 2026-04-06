# Exercise 1: Verify Your S3 Buckets

## What You Will Do
In this exercise, you will confirm that the three S3 buckets were automatically created and configured correctly by the CloudFormation template.

---

## Task 1: Open the S3 Console

1. Go to **AWS Management Console**
2. In the top search bar, search for **S3** → click **S3**
3. You should see a list of all your buckets

---

## Task 2: Verify the Source Bucket

1. Look for the bucket named **`s3auto-dev-sourcebucket`**
2. Click on it → go to the **Properties** tab
3. Confirm the following:
   - **Bucket Versioning** → shows **Enabled** ✅
   - **Default encryption** → shows **Enabled** ✅
4. Go to the **Permissions** tab
5. Confirm **Block Public Access** shows all four settings as **On** ✅

---

## Task 3: Verify the Destination Bucket

1. Go back to the S3 bucket list
2. Look for the bucket named **`s3auto-dev-destinationbucket`**
3. Click on it → go to the **Properties** tab
4. Confirm the following:
   - **Bucket Versioning** → shows **Enabled** ✅
5. Go to the **Permissions** tab
6. Confirm **Block Public Access** shows all four settings as **On** ✅

---

## Task 4: Verify the Website Bucket

1. Go back to the S3 bucket list
2. Look for the bucket named **`s3auto-dev-websitebucket`**
3. Click on it → go to the **Properties** tab
4. Confirm the following:
   - **Bucket Versioning** → shows **Enabled** ✅
   - **Static website hosting** → shows **Enabled** ✅
   - **Index document** → shows `index.html` ✅
   - **Error document** → shows `error.html` ✅
5. Go to the **Permissions** tab
6. Confirm **Block Public Access** shows all four settings as **Off** ✅

---

## Verify

Confirm all three buckets are visible in the S3 console:

| Bucket | Versioning | Public Access |
|--------|-----------|---------------|
| `s3auto-dev-sourcebucket` | ✅ Enabled | 🔒 Blocked |
| `s3auto-dev-destinationbucket` | ✅ Enabled | 🔒 Blocked |
| `s3auto-dev-websitebucket` | ✅ Enabled | 🌐 Public |

---

You are now ready for **Exercise 2: Verify Bucket Policies**
