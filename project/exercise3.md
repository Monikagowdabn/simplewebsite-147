# Exercise 3: Verify Lifecycle Rules

## What You Will Do
In this exercise, you will verify that lifecycle rules have been automatically configured on the source and website buckets by the CloudFormation template.

---

## What Are Lifecycle Rules?

Lifecycle rules automatically move your objects to cheaper storage classes based on their age:

| Days | Storage Class | Purpose |
|------|--------------|---------|
| 0 – 30 days | **S3 Standard** | Frequently accessed data |
| After 30 days | **Standard-IA** | Infrequently accessed, lower cost |
| After 60 days | **Intelligent-Tiering** | Auto-optimizes based on access patterns |

---

## Task 1: Verify Lifecycle Rule on the Source Bucket

1. Go to **S3** → click on **`s3auto-dev-sourcebucket`**
2. Click the **Management** tab
3. Scroll down to **Lifecycle rules**
4. Confirm the rule named **`AutoTierTransitionRule`** is listed ✅
5. Click on the rule to see details and confirm:
   - **Status:** Enabled ✅
   - **Scope:** Applies to all objects (Prefix is empty) ✅
   - **Transition 1:** Move to `Standard-IA` after **30 days** ✅
   - **Transition 2:** Move to `Intelligent-Tiering` after **60 days** ✅
<img width="1912" height="868" alt="image" src="https://github.com/user-attachments/assets/7c770412-7b84-4303-bac1-6b49cfdc3f15" />

---

## Task 2: Verify Lifecycle Rule on the Website Bucket

1. Go to **S3** → click on **`s3auto-dev-websitebucket`**
2. Click the **Management** tab
3. Scroll down to **Lifecycle rules**
4. Confirm the rule named **`WebsiteAssetLifecycle`** is listed ✅
5. Click on the rule to see details and confirm:
   - **Status:** Enabled ✅
   - **Scope:** Applies to all objects (Prefix is empty) ✅
   - **Transition 1:** Move to `Standard-IA` after **30 days** ✅
   - **Transition 2:** Move to `Intelligent-Tiering` after **60 days** ✅
<img width="1918" height="884" alt="image" src="https://github.com/user-attachments/assets/4eb65332-3d54-4005-a4a7-2ff674adb361" />

---

## Verify

| Bucket | Rule Name | 30 Days | 60 Days |
|--------|-----------|---------|---------|
| `s3auto-dev-sourcebucket` | ✅ AutoTierTransitionRule | Standard-IA | Intelligent-Tiering |
| `s3auto-dev-websitebucket` | ✅ WebsiteAssetLifecycle | Standard-IA | Intelligent-Tiering |

---

You are now ready for **Exercise 4: Verify Replication**
