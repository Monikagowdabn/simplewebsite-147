# Getting Started

## Welcome to the Lab

In this lab, your complete Amazon S3 infrastructure has already been automatically deployed using a **CloudFormation Template (CFT)**. You do not need to create anything manually.

Your job in each exercise is to **explore, verify, and understand** what was built for you.

---

## What Has Been Deployed For You

| Resource | Details |
|---|---|
| **Source Bucket** | `s3auto-dev-sourcebucket` — Private, versioning enabled, lifecycle rules configured |
| **Destination Bucket** | `s3auto-dev-destinationbucket` — Private, versioning enabled, replication target |
| **Website Bucket** | `s3auto-dev-websitebucket` — Public, static website hosting enabled |
| **IAM Role** | `S3ReplicationRole` — Allows S3 to replicate objects between buckets |
| **Lambda Function** | Auto-uploaded `index.html`, `error.html`, and a replication test object |

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
6. Note down the **WebsiteURL** — you will need it in Exercise 5

---

## Estimated Time

Approximately **30 minutes**

---

Let's get started with **Exercise 1!**
