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

---

## Task 2: Verify the IAM Replication Role

1. Go to **AWS Management Console** → search for **IAM** → click **IAM**
2. Click **Roles** in the left sidebar
3. Search for **`S3ReplicationRole`**
4. Click on the role and confirm:
   - **Trusted entity:** `s3.amazonaws.com` ✅
   - **Permissions policy:** `S3ReplicationPolicy` ✅
   - Policy allows actions: `GetObjectVersionForReplication`, `ReplicateObject`, `ReplicateDelete` ✅

---

## Task 3: Verify the Test Object in Source Bucket

1. Go to **S3** → click on **`s3auto-dev-sourcebucket`**
2. Click the **Objects** tab
3. Navigate to the folder **`replication-test/`**
4. Confirm **`test-object.txt`** is present ✅

> This file was automatically uploaded by the Lambda function when the stack was deployed.

---

## Task 4: Verify Replication in the Destination Bucket

1. Wait **2–3 minutes** after the stack was created
2. Go to **S3** → click on **`s3auto-dev-destinationbucket`**
3. Click the **Objects** tab
4. Navigate to **`replication-test/`**
5. Confirm **`test-object.txt`** has been replicated there ✅

> If the file is not yet visible, wait another minute and refresh the page.

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
