## ADD SUBSCRIPTION
Add a new subscription to the system
***

'**POST** {environment domain}/api/services/CRM/OrderSubscription/Update
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| connectedAccountId | String | Valid Stripe account ID | The unique identifier of the connected Stripe account, typically starting with "acct_" followed by alphanumeric characters |
***

**Request Body**

        {
        "connectedAccountId": "acct_1MD475HHdexuAbVt"

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

## UPDATE SUBSCRIPTIONS
Update an existing subscription's details
***

'**POST** {environment domain} /api/services/CRM/OrderSubscription/Update
***

### Request Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
| --- | --- | --- | --- |
| `contactId` | Integer | Any valid contact ID | The ID of the contact associated with the subscription. |
| `contactXref` | String | Any valid string | The external reference (xref) of the contact. |
| `leadId` | Integer | Any valid lead ID | The ID of the lead associated with the subscription. |
| `orderNumber` | String | Any valid string | The order number associated with the subscription. |
| `subscriptions` | Array of Objects | - | Contains the subscription information. |
| `subscriptions[].code` | String | Any valid string | The code of the subscription. |
| `subscriptions[].name` | String | Any valid string | The name of the subscription. |
| `subscriptions[].level` | String | Any valid string | The level of the subscription. |
| `subscriptions[].startDate` | Date | Any valid date | The start date of the subscription. |
| `subscriptions[].endDate` | Date | Any valid date | The end date of the subscription. |
| `subscriptions[].amount` | Decimal | Any valid decimal number | The amount of the subscription. |
| `products` | Array of Objects | - | Contains the product information. |
| `products[].productId` | Integer | Any valid product ID | The ID of the product. |
| `products[].productCode` | String | Any valid string | The code of the product. |
| `products[].paymentPeriodType` | String | `Monthly`, `Yearly` | The payment period type for the product. |
| `products[].hasRecurringBilling` | Boolean | `true`, `false` | Indicates whether the product has recurring billing. |
| `products[].endDate` | Date | Any valid date | The end date of the product. |
| `productId` | Integer | Any valid product ID | The ID of the product. |
| `productCode` | String | Any valid string | The code of the product. |
| `paymentPeriodType` | String | `Monthly`, `Yearly` | The payment period type for the product. |
| `hasRecurringBilling` | Boolean | `true`, `false` | Indicates whether the product has recurring billing. |
| `skipExisting` | Boolean | `true`, `false` | Indicates whether to skip existing subscriptions. |
***

**Request Body**

        {
        "contactId": 0,
        "contactXref": "string",
        "leadId": 0,
        "orderNumber": "string",
        "subscriptions": [
        {
        "code": "string",
        "name": "string",
        "level": "string",
        "startDate": "2024-04-29T06:59:51.875Z",
        "endDate": "2024-04-29T06:59:51.875Z",
        "amount": 0
        }
        ],
        "products": [
        {
        "productId": 0,
        "productCode": "string",
        "paymentPeriodType": "Monthly",
        "hasRecurringBilling": true,
        "endDate": "2024-04-29T06:59:51.875Z"
        }
        ],
        "productId": 0,
        "productCode": "string",
        "paymentPeriodType": "Monthly",
        "hasRecurringBilling": true,
        "skipExisting": true
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

## LIST SUBSCRIPTIONS
Retrieve a list of all subscriptions
***

'**GET** {environment domain}/api/services/CRM/OrderSubscription/GetSubscriptionHistory?contactId=contact_id
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| contact_id | String | Any valid string | The id of the contact |
        
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
