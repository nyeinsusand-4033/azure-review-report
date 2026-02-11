# Usage Guide

## Triggering the Function

The Azure Function is triggered by uploading a CSV file to the Azure Blob Storage container named `reviews`.

### 1. Prepare CSV File

Create a CSV file (e.g., `reviews.csv`) with the following headers:

```csv
product_id,user_id,rating,comment
101,501,5,Great product!
102,502,3,Average quality.
```

### 2. Upload to Blob Storage

You can upload the file using Azure Portal, Azure Storage Explorer, or Azure CLI.

**Using Azure CLI:**
```bash
az storage blob upload --account-name <storage-account-name> --container-name reviews --name reviews.csv --file reviews.csv
```

## Verifying Results

Once the file is uploaded, the Azure Function will process it automatically.

### 1. Check Function Logs

Go to your Function App in the Azure Portal and view the **Log Stream** or **Monitor** section to see real-time logs of the processing.

### 2. Verify MongoDB Data

Connect to your MongoDB database and check the `reviews` collection. You should see the new documents inserted.

```json
{
  "_id": "...",
  "product_id": 101,
  "user_id": 501,
  "rating": 5,
  "comment": "Great product!",
  "created_at": "2023-10-27T10:00:00.000Z"
}
```
