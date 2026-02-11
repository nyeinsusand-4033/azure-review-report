# Azure Review Report Import Function

This project contains an Azure Function App that automatically imports product reviews from CSV files uploaded to Azure Blob Storage into a MongoDB database.

## Features

-   **Blob Trigger**: Listens for new `.csv` files in the `reviews` container.
-   **CSV Parsing**: Reads and parses product, user, rating, and comment data.
-   **MongoDB Integration**: Inserts parsed reviews into a MongoDB `reviews` collection.

## Documentation

-   [**Setup Guide**](docs/SETUP.md): Instructions for setting up the project locally.
-   [**Deployment Guide**](docs/DEPLOYMENT.md): Steps to deploy the Function App to Azure.
-   [**Usage Guide**](docs/USAGE.md): How to trigger the function and verify the results.

## Project Structure

```
.
├── docs/                   # Documentation
│   ├── DEPLOYMENT.md
│   ├── SETUP.md
│   └── USAGE.md
├── function_app.py         # Function logic
├── host.json               # Host configuration
├── local.settings.json     # Local environment variables
├── requirements.txt        # Python dependencies
└── README.md               # Project overview
```
