# Exercise 2: Set Up Bucket Policies

## What You Will Do
In this exercise, you will attach policies to your buckets to control who can access them.

---

## Task 1: Add Policy to the Source Bucket

1. Go to **S3** → click on your **source bucket**
2. Click the **Permissions** tab
3. Scroll down to **Bucket policy** → click **Edit**
4. Paste the following policy *(replace `YOUR_ACCOUNT_ID` and `source-bucket-yourname`)*:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowReplicationRoleRead",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::YOUR_ACCOUNT_ID:role/s3-replication-role"
      },
      "Action": [
        "s3:GetObject",
        "s3:GetObjectVersion",
        "s3:GetObjectVersionAcl"
      ],
      "Resource": "arn:aws:s3:::source-bucket-yourname/*"
    }
  ]
}
```

5. Click **Save changes**

✅ Source bucket policy saved.

---

## Task 2: Add Policy to the Destination Bucket

1. Go to **S3** → click on your **destination bucket**
2. Click the **Permissions** tab
3. Scroll down to **Bucket policy** → click **Edit**
4. Paste the following policy *(replace `YOUR_ACCOUNT_ID` and `destination-bucket-yourname`)*:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowReplicationRoleWrite",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::YOUR_ACCOUNT_ID:role/s3-replication-role"
      },
      "Action": [
        "s3:ReplicateObject",
        "s3:ReplicateDelete",
        "s3:ReplicateTags"
      ],
      "Resource": "arn:aws:s3:::destination-bucket-yourname/*"
    }
  ]
}
```

5. Click **Save changes**

✅ Destination bucket policy saved.

---

## Task 3: Add Policy to the Website Bucket

1. Go to **S3** → click on your **website bucket**
2. Click the **Permissions** tab
3. Scroll down to **Bucket policy** → click **Edit**
4. Paste the following policy *(replace `website-bucket-yourname`)*:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::website-bucket-yourname/*"
    }
  ]
}
```

5. Click **Save changes**

✅ Website bucket policy saved.

---

## Verify

1. Go to each bucket → **Permissions** tab → **Bucket policy**
2. Confirm each bucket shows the correct policy you just added

---

You are now ready for **Exercise 3: Configure Lifecycle Rules**
