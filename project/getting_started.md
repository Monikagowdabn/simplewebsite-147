# Getting Started

## Welcome to the Lab

In this lab, your complete Amazon S3 infrastructure has already been automatically deployed using a **CloudFormation Template (CFT)**. You do not need to create anything manually.

Your job in each exercise is to **explore, verify, and understand** what was built for you.

---

## What Has Been Deployed For You

| Resource | Details |
|---|---|
| **Source Bucket** | `source-bucket-{DeploymentID}` — Private, versioning enabled, lifecycle rules configured |
| **Destination Bucket** | `destination-bucket-{DeploymentID}` — Private, versioning enabled, replication target |
| **Website Bucket** | `website-bucket-{DeploymentID}` — Public, static website hosting enabled |
| **IAM Role** | `S3ReplicationRole` — Allows S3 to replicate objects between buckets |
| **IAM Role** | `LambdaExecutionRole` — Allows Lambda to upload files to S3 |
| **Lambda Function** | `WebsiteFileUploaderFunction` — Auto-uploaded `index.html`, `error.html`, and a replication test object |

> **Note:** `{DeploymentID}` is a unique ID automatically injected by CloudLabs. Your actual bucket names will have this ID appended — for example: `source-bucket-abc123`.

---

## What You Will Do

| Exercise | What You Will Verify |
|---|---|
| Exercise 1 | Confirm your S3 buckets were created correctly |
| Exercise 2 | Verify bucket policies are in place |
| Exercise 3 | Check lifecycle rules are configured |
| Exercise 4 | Validate replication is working between buckets |
| Exercise 5 | Open your live static website |

---

## How to Access the AWS Console

1. On the **CloudLabs** portal, click **Start Lab**

2. Wait until the status turns **green**

3. Click **AWS** to open the AWS Management Console

4. In the top search bar, search for **CloudFormation**

5. Click on your stack → go to the **Outputs** tab

6. Note down the following output values — you will need them throughout the exercises:
   - **`SourceBucketName`** — your source bucket name
   - **`DestinationBucketName`** — your destination bucket name
   - **`WebsiteBucketName`** — your website bucket name
   - **`WebsiteURL`** — your live website URL (needed in Exercise 5)

---

## Estimated Time

Approximately **30 minutes**

---

Let's get started with **Exercise 1!**
