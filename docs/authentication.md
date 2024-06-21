# Authentication

The Upgrade Chat CRM API utilizes API keys for authentication. API keys are unique identifiers that allow the API to associate requests with your account and grant appropriate access privileges.

## Getting Your API Key

1. Log in to your Upgrade Chat CRM account.
2. Navigate to the "Settings" section.
3. Under the "API" tab, you can generate a new API key or view your existing keys.
4. Copy the API key, as you will need it for making authenticated requests.


## Using Your API Key

To authenticate your API requests, you need to include your API key in the `Authorization` header of your HTTP requests. The header should be formatted as follows:

```
Authorization: Bearer <your_api_key>
```

Replace `<your_api_key>` with the actual API key you obtained from your Upgrade Chat CRM account.

