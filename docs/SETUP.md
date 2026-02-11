# Setup Guide

## Prerequisites

Before running this project, ensure you have the following installed:

-   **Python 3.9+**
-   **Azure Functions Core Tools** version 4.x
-   **Azure CLI** (for deployment)
-   **MongoDB** (local or cloud instance like MongoDB Atlas or Azure Cosmos DB for MongoDB)

## Installation

1.  **Clone the Repository**
    ```bash
    git clone <repository-url>
    cd azure-review-report
    ```

2.  **Create a Virtual Environment**
    ```bash
    python -m venv .venv
    source .venv/bin/activate  # On Windows use: .venv\Scripts\activate
    ```

3.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

## Configuration

1.  Create a `local.settings.json` file if it doesn't exist (it is gitignored). Use the following template:

    ```json
    {
      "IsEncrypted": false,
      "Values": {
        "AzureWebJobsStorage": "UseDevelopmentStorage=true",
        "FUNCTIONS_WORKER_RUNTIME": "python",
        "MONGO_URI": "<your_mongo_connection_string>",
        "MONGO_DB_NAME": "<your_database_name>"
      }
    }
    ```

3.  Replace `<your_mongo_connection_string>` and `<your_database_name>` with your actual MongoDB details.

## Running Locally

1.  Start the Azure Function:
    ```bash
    func start
    ```

2.  The function will start and listen for blob triggers. You can simulate blob uploads using the Azure Storage Emulator or Azurite.
