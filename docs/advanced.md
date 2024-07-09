# Advanced Endpoints

## ADD/UPDATE CONTACT (USING IMPORT METHOD)
Add or update a contact using the import method.
***

'**POST** {environment domain}/api/services/CRM/Import/ImportContact
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| connectedAccountId | String | Valid Stripe account ID | The unique identifier of the connected Stripe account, typically starting with "acct_" followed by alphanumeric characters |
***

**Response Body**


        { 
        ---  
        }
  
        
***

**Sample Request**

        curl -X 'POST' \
        'https://crm.upgrade.chat/api/services/CRM/TenantPaymentSettings/SetStripeConnectedAccount' \
        -H 'accept: */*' \
        -H 'Content-Type: application/json;odata.metadata=minimal;odata.streaming=true' \
        -H 'Authorization: Bearer <your token>' \
        -d '{
        "connectedAccountId": "string"
        }'/'''

***
**Sample Response: 200 (Success)**

        {
        "leadRequestXref": "string",
        "contactId": 0
        }


***

## ADD OR UPDATE CONTACT EXTENDED (USING IMPORT METHOD)

Add or update a contact using the import method, with maximum parameters
***

'**POST** {environment domain}/api/services/CRM/Import/ImportContact
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| connectedAccountId | String | Valid Stripe account ID | The unique identifier of the connected Stripe account, typically starting with "acct_" followed by alphanumeric characters |
***

**Response Body**

        { 
        ---  
        }
        
        
***

**Sample Request**

        curl -X 'POST' \
        'https://crm.upgrade.chat/api/services/CRM/TenantPaymentSettings/SetStripeConnectedAccount' \
        -H 'accept: */*' \
        -H 'Content-Type: application/json;odata.metadata=minimal;odata.streaming=true' \
        -H 'Authorization: Bearer <your token>' \
        -d '{
        "connectedAccountId": "string"
        }'/'''

***
**Sample Response: 200 (Success)**

        {
        "leadRequestXref": "string",
        "contactId": 0
        }


***
