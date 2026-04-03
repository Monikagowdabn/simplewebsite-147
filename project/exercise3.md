# Exercise 3: Configure Lifecycle Rules

## What You Will Do
In this exercise, you will set up lifecycle rules on your buckets so that objects automatically move to cheaper storage classes over time.

---

## What Are Lifecycle Rules?

Lifecycle rules automatically move your objects to different storage classes based on age:

| Days | Storage Class | Cost |
|---|---|---|
| 0 – 30 days | S3 Standard | Normal |
| After 30 days | Standard-IA | Cheaper |
| After 60 days | Intelligent-Tiering | Cheapest |

---

## Task 1: Add Lifecycle Rule to the Source Bucket

1. Go to **S3** → click on your **source bucket**
2. Click the **Management** tab
3. Scroll down to **Lifecycle rules** → click **Create lifecycle rule**
4. Enter the following:
   - **Lifecycle rule name:** `lifecycle-rule`
   - **Choose a rule scope:** Select **Apply to all objects in the bucket**
   - Check the acknowledgement box
5. Under **Lifecycle rule actions**, check **Transition current versions of objects between storage classes**
6. Click **Add transition**:
   - **Storage class:** `Standard-IA`
   - **Days after object creation:** `30`
7. Click **Add transition** again:
   - **Storage class:** `Intelligent-Tiering`
   - **Days after object creation:** `60`
8. Click **Create rule**

✅ Lifecycle rule added to source bucket.

---

## Task 2: Add Lifecycle Rule to the Website Bucket

1. Go to **S3** → click on your **website bucket**
2. Click the **Management** tab
3. Scroll down to **Lifecycle rules** → click **Create lifecycle rule**
4. Enter the following:
   - **Lifecycle rule name:** `lifecycle-rule`
   - **Choose a rule scope:** Select **Apply to all objects in the bucket**
   - Check the acknowledgement box
5. Under **Lifecycle rule actions**, check **Transition current versions of objects between storage classes**
6. Click **Add transition**:
   - **Storage class:** `Standard-IA`
   - **Days after object creation:** `30`
7. Click **Add transition** again:
   - **Storage class:** `Intelligent-Tiering`
   - **Days after object creation:** `60`
8. Click **Create rule**

✅ Lifecycle rule added to website bucket.

---

## Verify

1. Go to **source bucket** → **Management** tab → **Lifecycle rules**
2. Confirm `lifecycle-rule` is listed and status shows **Enabled**
3. Repeat the same check for the **website bucket**

---

You are now ready for **Exercise 4: Set Up Replication**
