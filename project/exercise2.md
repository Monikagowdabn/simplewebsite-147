# Exercise 2: Verify Bucket Policies

## What You Will Do
In this exercise, you will verify that the correct bucket policies have been automatically attached to each bucket by the CloudFormation template.

---

## Task 1: Verify the Source Bucket Policy

1. Go to **S3** → click on **`s3auto-dev-sourcebucket`**
2. Click the **Permissions** tab
3. Scroll down to **Bucket policy**
4. Confirm the policy is present and contains the following:
   - **Sid:** `AllowReplicationRoleAccess` ✅
   - **Effect:** `Allow` ✅
   - **Actions include:** `s3:GetObjectVersionForReplication`, `s3:ListBucket` ✅
   - **Principal:** the `S3ReplicationRole` ARN ✅

> This policy allows the replication role to read objects from the source bucket.


<img width="1897" height="890" alt="image" src="https://github.com/user-attachments/assets/0724075c-03f9-4918-81a1-edd7ff57d42f" />

---

## Task 2: Verify the Destination Bucket Policy

1. Go to **S3** → click on **`s3auto-dev-destinationbucket`**
2. Click the **Permissions** tab
3. Scroll down to **Bucket policy**
4. Confirm the policy is present and contains the following:
   - **Sid:** `AllowReplicationWrite` ✅
   - **Effect:** `Allow` ✅
   - **Actions include:** `s3:ReplicateObject`, `s3:ReplicateDelete`, `s3:ReplicateTags` ✅
   - **Principal:** the `S3ReplicationRole` ARN ✅

> This policy allows the replication role to write replicated objects into the destination bucket.

<img width="1902" height="889" alt="image" src="https://github.com/user-attachments/assets/ba2344da-313c-4cb1-a3bc-4b1aa0e35399" />

---

## Task 3: Verify the Website Bucket Policy

1. Go to **S3** → click on **`s3auto-dev-websitebucket`**
2. Click the **Permissions** tab
3. Scroll down to **Bucket policy**
4. Confirm the policy is present and contains the following:
   - **Sid:** `PublicReadGetObject` ✅
   - **Effect:** `Allow` ✅
   - **Principal:** `*` (everyone) ✅
   - **Action:** `s3:GetObject` ✅

> This policy allows anyone on the internet to read files from the website bucket, which is required for public website hosting.
<img width="1896" height="877" alt="image" src="https://github.com/user-attachments/assets/1b8b614a-818f-4536-9a4d-9cf3afe4a948" />

---

## Verify

| Bucket | Policy | Purpose |
|--------|--------|---------|
| `s3auto-dev-sourcebucket` | ✅ AllowReplicationRoleAccess | Replication read access |
| `s3auto-dev-destinationbucket` | ✅ AllowReplicationWrite | Replication write access |
| `s3auto-dev-websitebucket` | ✅ PublicReadGetObject | Public website access |

---

You are now ready for **Exercise 3: Verify Lifecycle Rules**
