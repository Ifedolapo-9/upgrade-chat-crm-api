## ADD INVOICE
Add a new invoice to the system
***

'**POST** {environment domain}/api/services/CRM/Invoice/Create
***

### Request Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
| --- | --- | --- | --- |
| `contactId` | Integer | Any valid contact ID | The ID of the contact associated with the order. |
| `groupId` | String | Any valid string | The ID of the group associated with the order. |
| `orderId` | Integer | Any valid order ID | The ID of the order. |
| `orderNumber` | String | Any valid string | The number of the order. |
| `leadId` | Integer | Any valid lead ID | The ID of the lead associated with the order. |
| `status` | String | `Draft`, `Pending`, `Paid`, `Cancelled`, `Refunded` | The status of the order. |
| `number` | String | Any valid string | The number of the order. |
| `date` | Date | Any valid date | The date of the order. |
| `dueDate` | Date | Any valid date | The due date of the order. |
| `subscriptionStartOn` | Date | Any valid date | The start date of the subscription. |
| `couponCode` | String | Any valid string | The coupon code applied to the order. |
| `currencyId` | String | Any valid currency ID | The ID of the currency for the order. |
| `grandTotal` | Decimal | Any valid decimal number | The grand total of the order. |
| `discountTotal` | Decimal | Any valid decimal number | The total discount applied to the order. |
| `shippingTotal` | Decimal | Any valid decimal number | The total shipping cost for the order. |
| `taxTotal` | Decimal | Any valid decimal number | The total tax for the order. |
| `billingAddress` | Object | - | Contains the billing address information. |
| `billingAddress.countryId` | String | Any valid country ID | The ID of the country for the billing address. |
| `billingAddress.stateId` | String | Any valid state ID | The ID of the state for the billing address. |
| `billingAddress.stateName` | String | Any valid string | The name of the state for the billing address. |
| `billingAddress.city` | String | Any valid string | The city for the billing address. |
| `billingAddress.zip` | String | Any valid zip code | The zip code for the billing address. |
| `billingAddress.neighborhood` | String | Any valid string | The neighborhood for the billing address. |
| `billingAddress.address1` | String | Any valid string | The first line of the billing address. |
| `billingAddress.address2` | String | Any valid string | The second line of the billing address. |
| `billingAddress.firstName` | String | Any valid string | The first name for the billing address. |
| `billingAddress.lastName` | String | Any valid string | The last name for the billing address. |
| `billingAddress.company` | String | Any valid string | The company for the billing address. |
| `billingAddress.email` | String | Any valid email address | The email address for the billing address. |
| `billingAddress.phone` | String | Any valid phone number | The phone number for the billing address. |
| `shippingAddress` | Object | - | Contains the shipping address information. |
| `shippingAddress.countryId` | String | Any valid country ID | The ID of the country for the shipping address. |
| `shippingAddress.stateId` | String | Any valid state ID | The ID of the state for the shipping address. |
| `shippingAddress.stateName` | String | Any valid string | The name of the state for the shipping address. |
| `shippingAddress.city` | String | Any valid string | The city for the shipping address. |
| `shippingAddress.zip` | String | Any valid zip code | The zip code for the shipping address. |
| `shippingAddress.neighborhood` | String | Any valid string | The neighborhood for the shipping address. |
| `shippingAddress.address1` | String | Any valid string | The first line of the shipping address. |
| `shippingAddress.address2` | String | Any valid string | The second line of the shipping address. |
| `shippingAddress.firstName` | String | Any valid string | The first name for the shipping address. |
| `shippingAddress.lastName` | String | Any valid string | The last name for the shipping address. |
| `shippingAddress.company` | String | Any valid string | The company for the shipping address. |
| `shippingAddress.email` | String | Any valid email address | The email address for the shipping address. |
| `shippingAddress.phone` | String | Any valid phone number | The phone number for the shipping address. |
| `description` | String | Any valid string | The description of the order. |
| `note` | String | Any valid string | The note for the order. |
| `forbiddenPaymentMethods` | Integer | Any valid integer | The forbidden payment methods for the order. |
| `lines` | Array of Objects | - | Contains the order lines. |
| `lines[].quantity` | Integer | Any valid integer | The quantity of the order line. |
| `lines[].rate` | Decimal | Any valid decimal number | The rate of the order line. |
| `lines[].total` | Decimal | Any valid decimal number | The total of the order line. |
| `lines[].commissionableAmount` | Decimal | Any valid decimal number | The commissionable amount of the order line. |
| `lines[].unitId` | String | `Day`, `Month`, `Year` | The unit ID for the order line. |
| `lines[].productCode` | String | Any valid string | The product code for the order line. |
| `lines[].description` | String | Any valid string | The description of the order line. |
| `lines[].sortOrder` | Integer | Any valid integer | The sort order of the order line. |
| `bypassValidation` | Boolean | `true`, `false` | Indicates whether to bypass validation for the order.
***

**Request Body**

        {
        "contactId": 0,
        "groupId": "string",
        "orderId": 0,
        "orderNumber": "string",
        "leadId": 0,
        "status": "Draft",
        "number": "string",
        "date": "2024-04-29T05:43:42.978Z",
        "dueDate": "2024-04-29T05:43:42.978Z",
        "subscriptionStartOn": "2024-04-29T05:43:42.978Z",
        "couponCode": "string",
        "currencyId": "string",
        "grandTotal": 0,
        "discountTotal": 0,
        "shippingTotal": 0,
        "taxTotal": 0,
        "billingAddress": {
        "countryId": "string",
        "stateId": "string",
        "stateName": "string",
        "city": "string",
        "zip": "string",
        "neighborhood": "string",
        "address1": "string",
        "address2": "string",
        "firstName": "string",
        "lastName": "string",
        "company": "string",
        "email": "string",
        "phone": "string"
        },
        "shippingAddress": {
        "countryId": "string",
        "stateId": "string",
        "stateName": "string",
        "city": "string",
        "zip": "string",
        "neighborhood": "string",
        "address1": "string",
        "address2": "string",
        "firstName": "string",
        "lastName": "string",
        "company": "string",
        "email": "string",
        "phone": "string"
        },
        "description": "string",
        "note": "string",
        "forbiddenPaymentMethods": 1,
        "lines": [
        {
        "quantity": 0,
        "rate": 0,
        "total": 0,
        "commissionableAmount": 0,
        "unitId": "Day",
        "productCode": "string",
        "description": "string",
        "sortOrder": 0
        }
        ],
        "bypassValidation": true
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

## UPDATE INVOICE
Update an existing invoice's details
***

'**PUT** {environment domain}/api/services/CRM/Invoice/Update


***

### Request Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
| --- | --- | --- | --- |
| `id` | Integer | Any valid ID | The ID of the order. |
| `status` | String | `Draft`, `Pending`, `Paid`, `Cancelled`, `Refunded` | The status of the order. |
| `number` | String | Any valid string | The number of the order. |
| `date` | Date | Any valid date | The date of the order. |
| `dueDate` | Date | Any valid date | The due date of the order. |
| `subscriptionStartOn` | Date | Any valid date | The start date of the subscription. |
| `couponCode` | String | Any valid string | The coupon code applied to the order. |
| `currencyId` | String | Any valid currency ID | The ID of the currency for the order. |
| `grandTotal` | Decimal | Any valid decimal number | The grand total of the order. |
| `discountTotal` | Decimal | Any valid decimal number | The total discount applied to the order. |
| `shippingTotal` | Decimal | Any valid decimal number | The total shipping cost for the order. |
| `taxTotal` | Decimal | Any valid decimal number | The total tax for the order. |
| `billingAddress` | Object | - | Contains the billing address information. |
| `billingAddress.countryId` | String | Any valid country ID | The ID of the country for the billing address. |
| `billingAddress.stateId` | String | Any valid state ID | The ID of the state for the billing address. |
| `billingAddress.stateName` | String | Any valid string | The name of the state for the billing address. |
| `billingAddress.city` | String | Any valid string | The city for the billing address. |
| `billingAddress.zip` | String | Any valid zip code | The zip code for the billing address. |
| `billingAddress.neighborhood` | String | Any valid string | The neighborhood for the billing address. |
| `billingAddress.address1` | String | Any valid string | The first line of the billing address. |
| `billingAddress.address2` | String | Any valid string | The second line of the billing address. |
| `billingAddress.firstName` | String | Any valid string | The first name for the billing address. |
| `billingAddress.lastName` | String | Any valid string | The last name for the billing address. |
| `billingAddress.company` | String | Any valid string | The company for the billing address. |
| `billingAddress.email` | String | Any valid email address | The email address for the billing address. |
| `billingAddress.phone` | String | Any valid phone number | The phone number for the billing address. |
| `shippingAddress` | Object | - | Contains the shipping address information. |
| `shippingAddress.countryId` | String | Any valid country ID | The ID of the country for the shipping address. |
| `shippingAddress.stateId` | String | Any valid state ID | The ID of the state for the shipping address. |
| `shippingAddress.stateName` | String | Any valid string | The name of the state for the shipping address. |
| `shippingAddress.city` | String | Any valid string | The city for the shipping address. |
| `shippingAddress.zip` | String | Any valid zip code | The zip code for the shipping address. |
| `shippingAddress.neighborhood` | String | Any valid string | The neighborhood for the shipping address. |
| `shippingAddress.address1` | String | Any valid string | The first line of the shipping address. |
| `shippingAddress.address2` | String | Any valid string | The second line of the shipping address. |
| `shippingAddress.firstName` | String | Any valid string | The first name for the shipping address. |
| `shippingAddress.lastName` | String | Any valid string | The last name for the shipping address. |
| `shippingAddress.company` | String | Any valid string | The company for the shipping address. |
| `shippingAddress.email` | String | Any valid email address | The email address for the shipping address. |
| `shippingAddress.phone` | String | Any valid phone number | The phone number for the shipping address. |
| `description` | String | Any valid string | The description of the order. |
| `note` | String | Any valid string | The note for the order. |
| `forbiddenPaymentMethods` | Integer | Any valid integer | The forbidden payment methods for the order. |
| `lines` | Array of Objects | - | Contains the order lines. |
| `lines[].id` | Integer | Any valid ID | The ID of the order line. |
| `lines[].quantity` | Integer | Any valid integer | The quantity of the order line. |
| `lines[].rate` | Decimal | Any valid decimal number | The rate of the order line. |
| `lines[].total` | Decimal | Any valid decimal number | The total of the order line. |
| `lines[].commissionableAmount` | Decimal | Any valid decimal number | The commissionable amount of the order line. |
| `lines[].unitId` | String | `Day`, `Month`, `Year` | The unit ID for the order line. |
| `lines[].productCode` | String | Any valid string | The product code for the order line. |
| `lines[].description` | String | Any valid string | The description of the order line. |
| `lines[].sortOrder` | Integer | Any valid integer | The sort order of the order line. |
| `bypassValidation` | Boolean | `true`, `false` | Indicates whether to bypass validation for the order. |
***

**Request Body**

        {
        "id": 0,
        "status": "Draft",
        "number": "string",
        "date": "2024-04-29T05:49:20.526Z",
        "dueDate": "2024-04-29T05:49:20.526Z",
        "subscriptionStartOn": "2024-04-29T05:49:20.526Z",
        "couponCode": "string",
        "currencyId": "string",
        "grandTotal": 0,
        "discountTotal": 0,
        "shippingTotal": 0,
        "taxTotal": 0,
        "billingAddress": {
        "countryId": "string",
        "stateId": "string",
        "stateName": "string",
        "city": "string",
        "zip": "string",
        "neighborhood": "string",
        "address1": "string",
        "address2": "string",
        "firstName": "string",
        "lastName": "string",
        "company": "string",
        "email": "string",
        "phone": "string"
        },
        "shippingAddress": {
        "countryId": "string",
        "stateId": "string",
        "stateName": "string",
        "city": "string",
        "zip": "string",
        "neighborhood": "string",
        "address1": "string",
        "address2": "string",
        "firstName": "string",
        "lastName": "string",
        "company": "string",
        "email": "string",
        "phone": "string"
        },
        "description": "string",
        "note": "string",
        "forbiddenPaymentMethods": 1,
        "lines": [
        {
        "id": 0,
        "quantity": 0,
        "rate": 0,
        "total": 0,
        "commissionableAmount": 0,
        "unitId": "Day",
        "productCode": "string",
        "description": "string",
        "sortOrder": 0
        }
        ],
        "bypassValidation": true
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

## GET INVOICE
Retrieve invoice info 
***

'**GET** {environment domain}/api/services/CRM/Invoice/GetInvoiceInfo?id={invoice_id}
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| invoice_id | String | Any valid string | The id of an invoice |
        
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

## DELETE INVOICE
Remove an invoice from the system
***

'**DELETE** {environment domain}/api/services/CRM/Invoice/DeleteInvoice?id={invoice_id}
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| invoice_id | String | Any valid string | The id of an invoice |
        
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
