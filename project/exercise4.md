# Exercise 4: Verify Replication

## What You Will Do
In this exercise, you will verify that replication has been automatically configured between the source and destination buckets, and confirm that the test object uploaded by Lambda has been replicated successfully.

---

## Task 1: Verify Replication Rule on the Source Bucket

1. Go to **S3** → click on **`s3auto-dev-sourcebucket`**
2. Click the **Management** tab
3. Scroll down to **Replication rules**
4. Confirm the rule named **`FullBucketReplicationRule`** is listed ✅
5. Click on the rule to see details and confirm:
   - **Status:** Enabled ✅
   - **Scope:** Entire bucket (empty prefix) ✅
   - **Destination bucket:** `s3auto-dev-destinationbucket` ✅
   - **Storage class:** Standard ✅
   - **IAM Role:** `S3ReplicationRole` ✅
<img width="1919" height="875" alt="image" src="https://github.com/user-attachments/assets/01075873-4eb7-46d0-b690-3d58e64180cf" />

---

## Task 2: Verify the IAM Replication Role

1. Go to **AWS Management Console** → search for **IAM** → click **IAM**
2. Click **Roles** in the left sidebar
3. Search for **`S3ReplicationRole`**
4. Click on the role and confirm:
   - **Trusted entity:** `s3.amazonaws.com` ✅
   - **Permissions policy:** `S3ReplicationPolicy` ✅
   - Policy allows actions: `GetObjectVersionForReplication`, `ReplicateObject`, `ReplicateDelete` ✅
<img width="1914" height="863" alt="image" src="https://github.com/user-attachments/assets/3a0b4a75-0b49-4bd3-ae37-d441e53bc58a" />

---

## Task 3: Verify the Test Object in Source Bucket

1. Go to **S3** → click on **`s3auto-dev-sourcebucket`**
2. Click the **Objects** tab
3. Navigate to the folder **`replication-test/`**
4. Confirm **`test-object.txt`** is present ✅

> This file was automatically uploaded by the Lambda function when the stack was deployed.
<img width="1903" height="770" alt="image" src="https://github.com/user-attachments/assets/25c696e9-e573-49d2-a2ca-06ea4953d863" />

---

## Task 4: Verify Replication in the Destination Bucket

1. Wait **2–3 minutes** after the stack was created
2. Go to **S3** → click on **`s3auto-dev-destinationbucket`**
3. Click the **Objects** tab
4. Navigate to **`replication-test/`**
5. Confirm **`test-object.txt`** has been replicated there ✅

> If the file is not yet visible, wait another minute and refresh the page.
<img width="1912" height="860" alt="image" src="https://github.com/user-attachments/assets/bce3f575-c191-47fe-8982-2e970cd3f3bc" />

---

## Verify

| Check | Status |
|-------|--------|
| Replication rule `FullBucketReplicationRule` exists on source bucket | ✅ |
| IAM Role `S3ReplicationRole` exists with correct permissions | ✅ |
| `test-object.txt` exists in source bucket | ✅ |
| `test-object.txt` replicated to destination bucket | ✅ |

---

You are now ready for **Exercise 5: View Your Static Website**
