# Summary

## Congratulations! 🎉

You have successfully completed all five exercises. Here is a recap of everything that was automatically deployed and what you verified.

---

## What Was Automatically Deployed by CloudFormation

### Exercise 1 — S3 Buckets Created

- **`source-bucket-{DeploymentID}`** — Private bucket with versioning enabled
- **`destination-bucket-{DeploymentID}`** — Private bucket with versioning enabled, lifecycle rules configured
- **`website-bucket-{DeploymentID}`** — Public bucket with versioning and website hosting enabled

### Exercise 2 — Bucket Policies Attached

- **Source bucket** — Policy (`AllowReplicationRoleAccess`) allows the `S3ReplicationRole` to read objects
- **Destination bucket** — Policy (`AllowReplicationWrite`) allows the `S3ReplicationRole` to write replicated objects
- **Website bucket** — Policy (`PublicReadGetObject`) allows public read access for static website hosting

### Exercise 3 — Lifecycle Rules Configured

- **Source bucket** — `AutoTierTransitionRule` transitions objects to Standard-IA after 30 days, then Intelligent-Tiering after 60 days
- **Destination bucket** — `DestinationTierTransitionRule` applies the same transitions automatically
- **Website bucket** — `WebsiteAssetLifecycle` applies the same transitions automatically

### Exercise 4 — Replication Configured

- **Replication rule** `FullBucketReplicationRule` set up on source bucket pointing to `destination-bucket-{DeploymentID}`
- **IAM Role** `S3ReplicationRole` created with `S3ReplicationPolicy` to give S3 permission to replicate objects
- **IAM Role** `LambdaExecutionRole` created with `S3WritePolicy` to allow Lambda to upload files to S3
- **Test object** `replication-test/test-object.txt` auto-uploaded to source bucket and replicated to destination bucket

### Exercise 5 — Static Website Hosted

- **`index.html`** — Vision Board homepage auto-uploaded by `WebsiteFileUploaderFunction` Lambda
- **`error.html`** — Custom 404 page auto-uploaded by `WebsiteFileUploaderFunction` Lambda
- **`WebsiteURL`** — Live public website endpoint available in CloudFormation Outputs

---

## CloudFormation Outputs Reference

| Output Key | Description |
|---|---|
| `SourceBucketName` | Name of the source bucket |
| `SourceBucketARN` | ARN of the source bucket |
| `DestinationBucketName` | Name of the destination bucket |
| `DestinationBucketARN` | ARN of the destination bucket |
| `WebsiteBucketName` | Name of the website bucket |
| `WebsiteBucketARN` | ARN of the website bucket |
| `WebsiteURL` | Live static website URL |
| `ReplicationRoleARN` | ARN of the S3 replication IAM role |
| `ReplicationTestObjectPath` | S3 path of the replication test object |

---

## Your Final Architecture

```
CloudFormation Template
         |
         ├── S3ReplicationRole (IAM)
         │       └── S3ReplicationPolicy
         │
         ├── LambdaExecutionRole (IAM)
         │       ├── AWSLambdaBasicExecutionRole (managed)
         │       └── S3WritePolicy (inline)
         │
         ├── source-bucket-{DeploymentID}
         │       ├── Versioning: Enabled
         │       ├── Block Public Access: ON
         │       ├── Lifecycle: 30d → Standard-IA → 60d → Intelligent-Tiering
         │       ├── Replication Rule → destination-bucket-{DeploymentID}
         │       └── replication-test/test-object.txt (auto-uploaded by Lambda)
         │
         ├── destination-bucket-{DeploymentID}
         │       ├── Versioning: Enabled
         │       ├── Block Public Access: ON
         │       ├── Lifecycle: 30d → Standard-IA → 60d → Intelligent-Tiering
         │       └── replication-test/test-object.txt (replicated automatically)
         │
         ├── website-bucket-{DeploymentID}
         │       ├── Versioning: Enabled
         │       ├── Block Public Access: OFF
         │       ├── Static Website Hosting: Enabled
         │       ├── Lifecycle: 30d → Standard-IA → 60d → Intelligent-Tiering
         │       ├── index.html (auto-uploaded by Lambda)
         │       └── error.html (auto-uploaded by Lambda)
         │
         └── WebsiteFileUploaderFunction (Lambda)
                 └── Uploads index.html, error.html, and replication test object on deploy
```

---

## Key Takeaway

Everything in this lab was deployed using a single **CloudFormation Template** — no manual steps were needed to create buckets, attach policies, configure lifecycle rules, set up replication, or upload website files. This is the power of **Infrastructure as Code (IaC)**!

---

## Well Done!

You have successfully verified a complete Amazon S3 infrastructure including storage, policies, lifecycle management, replication, and static website hosting — all automated through CloudFormation! 🚀
