
# Error Handling

The Upgrade Chat CRM API uses standard HTTP status codes to indicate the success or failure of an API request. Here are some common status codes and their meanings:

- **200 OK:** The request was successful.
- **400 Bad Request:** The request was malformed or missing required parameters.
- **401 Unauthorized:** The request was not authenticated or the provided API key is invalid.
- **404 Not Found:** The requested resource does not exist.
- **500 Internal Server Error:** An internal server error occurred while processing the request.

In case of an error, the API will respond with a JSON object containing an `error` key with a descriptive error message. For example:

```json
{
  "error": "Invalid API key provided"
}
```

If you encounter an error, review the error message and troubleshoot accordingly. Common issues may include providing an invalid API key, missing required parameters, or sending malformed requests.