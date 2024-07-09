## ADD COUPONS
Add a new coupon to the system
***

'**POST** {environment domain}/api/services/CRM/Coupon/CreateCoupon
***

### Request Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
| --- | --- | --- | --- |
| `code` | String | Any valid string | The code of the coupon. |
| `description` | String | Any valid string | The description of the coupon. |
| `type` | String | `Percentage`, `FixedAmount` | The type of the coupon. |
| `duration` | String | `Once`, `Recurring` | The duration of the coupon. |
| `amountOff` | Decimal | Any valid decimal number | The amount off for the coupon (if type is `FixedAmount`). |
| `percentOff` | Decimal | Any valid decimal number (0-100) | The percentage off for the coupon (if type is `Percentage`). |
| `currencyId` | String | Any valid currency ID | The ID of the currency for the coupon. |
| `activationDate` | Date | Any valid date | The date the coupon becomes active. |
| `deactivationDate` | Date | Any valid date | The date the coupon becomes inactive. |
| `isArchived` | Boolean | `true`, `false` | Indicates whether the coupon is archived. |
***

**Request Body**
        {
        "code": "string",
        "description": "string",
        "type": "Percentage",
        "duration": "Once",
        "amountOff": 1000000,
        "percentOff": 100,
        "currencyId": "string",
        "activationDate": "2024-04-29T05:59:19.616Z",
        "deactivationDate": "2024-04-29T05:59:19.616Z",
        "isArchived": true
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

## UPDATE COUPONS
Update details of existing coupon
***

'**PUT** {environment domain}/api/services/CRM/Coupon/UpdateCoupon
***

### Request Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
| --- | --- | --- | --- |
| `code` | String | Any valid string | The code of the coupon. |
| `description` | String | Any valid string | The description of the coupon. |
| `type` | String | `Percentage`, `FixedAmount` | The type of the coupon. |
| `duration` | String | `Once`, `Recurring` | The duration of the coupon. |
| `amountOff` | Decimal | Any valid decimal number | The amount off for the coupon (if type is `FixedAmount`). |
| `percentOff` | Decimal | Any valid decimal number (0-100) | The percentage off for the coupon (if type is `Percentage`). |
| `currencyId` | String | Any valid currency ID | The ID of the currency for the coupon. |
| `activationDate` | Date | Any valid date | The date the coupon becomes active. |
| `deactivationDate` | Date | Any valid date | The date the coupon becomes inactive. |
| `isArchived` | Boolean | `true`, `false` | Indicates whether the coupon is archived. |
***

**Request Body**

        {
        "id": 0,
        "code": "string",
        "description": "string",
        "type": "Percentage",
        "duration": "Once",
        "amountOff": 1000000,
        "percentOff": 100,
        "currencyId": "string",
        "activationDate": "2024-04-29T06:02:20.763Z",
        "deactivationDate": "2024-04-29T06:02:20.763Z",
        "isArchived": true
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

## GET COUPON
Retrieve coupon's details
***

'**POST** {environment domain}/api/services/CRM/Coupon/GetCoupon?id={coupon_id}
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| coupon_id | String | Any valid string | The id of a coupon |
        
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

## DELETE COUPON
Remove a coupon from the system using their its ID
***

'**POST** {environment domain}/api/services/CRM/Coupon/DeleteCoupon?id={coupon_id}
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| coupon_id | String | Any valid string | The id of a coupon |

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