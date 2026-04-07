# Exercise 1: Verify Your S3 Buckets

## What You Will Do

In this exercise, you will confirm that the three S3 buckets were automatically created and configured correctly by the CloudFormation template.

> **Tip:** Your bucket names include your unique CloudLabs Deployment ID. Go to **CloudFormation → your stack → Outputs tab** to find the exact bucket names under `SourceBucketName`, `DestinationBucketName`, and `WebsiteBucketName`.

---

## Task 1: Open the S3 Console

1. Go to **AWS Management Console**

2. In the top search bar, search for **S3** → click **S3**

3. You should see a list of all your buckets

   <img width="1894" height="871" alt="image" src="https://github.com/user-attachments/assets/4ade5501-22d9-426c-958a-85546d6e334e" />

---

## Task 2: Verify the Source Bucket

1. Look for the bucket named **`source-bucket-{DeploymentID}`**

2. Click on it → go to the **Properties** tab

3. Confirm the following:

   - **Bucket Versioning** → shows **Enabled** ✅

   - **Default encryption** → shows **Enabled** ✅

4. Go to the **Permissions** tab

5. Confirm **Block Public Access** shows all four settings as **On** ✅

   <img width="1872" height="855" alt="image" src="https://github.com/user-attachments/assets/db418b76-f847-43b7-94c2-860ae88fbb90" />

   <img width="1892" height="696" alt="image" src="https://github.com/user-attachments/assets/488f6609-eced-4212-b582-ed99eff73d87" />

---

## Task 3: Verify the Destination Bucket

1. Go back to the S3 bucket list

2. Look for the bucket named **`destination-bucket-{DeploymentID}`**

3. Click on it → go to the **Properties** tab

4. Confirm the following:

   - **Bucket Versioning** → shows **Enabled** ✅

5. Go to the **Permissions** tab

6. Confirm **Block Public Access** shows all four settings as **On** ✅

   <img width="1895" height="652" alt="image" src="https://github.com/user-attachments/assets/f70930c1-9c27-4a7e-8edd-3b7aee161fc3" />

   <img width="1915" height="502" alt="image" src="https://github.com/user-attachments/assets/913ec1bb-cb09-49ce-a404-ffaf598e6146" />

---

## Task 4: Verify the Website Bucket

1. Go back to the S3 bucket list

2. Look for the bucket named **`website-bucket-{DeploymentID}`**

3. Click on it → go to the **Properties** tab

4. Confirm the following:

   - **Bucket Versioning** → shows **Enabled** ✅

   - **Static website hosting** → shows **Enabled** ✅

   - **Index document** → shows `index.html` ✅

   - **Error document** → shows `error.html` ✅

5. Go to the **Permissions** tab

6. Confirm **Block Public Access** shows all four settings as **Off** ✅

   <img width="1903" height="656" alt="image" src="https://github.com/user-attachments/assets/687caf35-9a38-4bc3-8596-f8d8f18b3cb3" />

   <img width="1890" height="865" alt="image" src="https://github.com/user-attachments/assets/69b37ff7-69d7-44b1-91a2-df61d2cc0c7a" />

   <img width="1918" height="482" alt="image" src="https://github.com/user-attachments/assets/0aa56cdf-ba73-46e0-b222-f7a4020495fa" />

---

## Verify

Confirm all three buckets are visible in the S3 console:

| Bucket | Versioning | Public Access |
|--------|-----------|---------------|
| `source-bucket-{DeploymentID}` | ✅ Enabled | 🔒 Blocked |
| `destination-bucket-{DeploymentID}` | ✅ Enabled | 🔒 Blocked |
| `website-bucket-{DeploymentID}` | ✅ Enabled | 🌐 Public |

---

You are now ready for **Exercise 2: Verify Bucket Policies**
