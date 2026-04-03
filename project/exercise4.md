# Exercise 4: Set Up Replication

## What You Will Do
In this exercise, you will set up automatic replication from your source bucket to your destination bucket. Any object you upload to the source bucket will automatically appear in the destination bucket.

---

## Task 1: Set Up Replication on the Source Bucket

1. Go to **S3** → click on your **source bucket**
2. Click the **Management** tab
3. Scroll down to **Replication rules** → click **Create replication rule**
4. Enter the following:
   - **Replication rule name:** `replication-rule`
   - **Status:** Enabled
5. Under **Source bucket**:
   - **Choose a rule scope:** Select **Apply to all objects in the bucket**
6. Under **Destination**:
   - Select **Choose a bucket in this account**
   - Click **Browse S3** and select your `destination-bucket-yourname`
7. Under **IAM role**:
   - Select **Create new role**
8. Click **Save**

✅ Replication rule created.

---

## Task 2: Upload a Test Object to Validate Replication

1. Go to **S3** → click on your **source bucket**
2. Click **Upload**
3. Click **Add files**
4. Create a simple text file on your computer called `test-object.txt` with any content
5. Select the file and click **Upload**
6. Click **Close** once upload is complete

---

## Task 3: Verify Replication

1. Wait **2–3 minutes** for replication to complete
2. Go to **S3** → click on your **destination bucket**
3. Confirm `test-object.txt` appears in the destination bucket

✅ Replication is working correctly.

---

## Verify Replication Rule

1. Go to **source bucket** → **Management** tab → **Replication rules**
2. Confirm `replication-rule` shows:
   - **Status:** Enabled
   - **Destination:** your destination bucket name
   - **Scope:** Entire bucket

---

You are now ready for **Exercise 5: Host a Static Website**
