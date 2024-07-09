## ADD PRODUCTS
Add a new product to the system
***

'**POST** {environment domain}/api/services/CRM/Product/CreateProduct
***

### Request Parameters
## Upgrade.chat API Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
| --- | --- | --- | --- |
| `code` | String | Any valid string | The code of the product. |
| `name` | String | Any valid string | The name of the product. |
| `description` | String | Any valid string | The description of the product. |
| `descriptionHtml` | String | Any valid string | The HTML description of the product. |
| `groupId` | Integer | Any valid group ID | The ID of the group the product belongs to. |
| `groupName` | String | Any valid string | The name of the group the product belongs to. |
| `type` | String | `General` | The type of the product. |
| `price` | Decimal | Any valid decimal number | The price of the product. |
| `currencyId` | String | Any valid currency ID | The ID of the currency for the price. |
| `commissionableAmount` | Decimal | Any valid decimal number | The commissionable amount for the product. |
| `maxCommissionRate` | Decimal | Any valid decimal number | The maximum commission rate for the product. |
| `maxCommissionRateTier2` | Decimal | Any valid decimal number | The maximum commission rate for tier 2 of the product. |
| `unit` | String | `Day` | The unit of the product. |
| `stripeXref` | String | Any valid string | The Stripe cross-reference (xref) for the product. |
| `paypalXref` | String | Any valid string | The PayPal cross-reference (xref) for the product. |
| `downgradeProductId` | Integer | Any valid product ID | The ID of the downgrade product. |
| `isPublished` | Boolean | `true`, `false` | Indicates whether the product is published. |
| `publicName` | String | Any valid string | The public name of the product. |
| `publishDate` | Date | Any valid date | The date the product was published. |
| `publicAllowCoupon` | Boolean | `true`, `false` | Indicates whether coupons are allowed for the public version of the product. |
| `createUser` | Boolean | `true`, `false` | Indicates whether to create a user for the product. |
| `productServices` | Array of Objects | - | Contains the services associated with the product. |
| `productServices[].memberServiceId` | Integer | Any valid member service ID | The ID of the member service. |
| `productServices[].memberServiceLevelId` | Integer | Any valid member service level ID | The ID of the member service level. |
| `productSubscriptionOptions` | Array of Objects | - | Contains the subscription options for the product. |
| `productSubscriptionOptions[].frequency` | String | `Monthly` | The frequency of the subscription. |
| `productSubscriptionOptions[].signupFee` | Decimal | Any valid decimal number | The signup fee for the subscription. |
| `productSubscriptionOptions[].commissionableSignupFeeAmount` | Decimal | Any valid decimal number | The commissionable amount for the signup fee. |
| `productSubscriptionOptions[].fee` | Decimal | Any valid decimal number | The fee for the subscription. |
| `productSubscriptionOptions[].commissionableFeeAmount` | Decimal | Any valid decimal number | The commissionable amount for the fee. |
| `productSubscriptionOptions[].trialDayCount` | Integer | Any valid integer | The number of trial days for the subscription. |
| `productSubscriptionOptions[].customPeriodCount` | Integer | Any valid integer | The number of custom periods for the subscription. |
| `productSubscriptionOptions[].customPeriodType` | String | `Days` | The type of custom period for the subscription. |
| `productSubscriptionOptions[].cycles` | Integer | Any valid integer | The number of cycles for the subscription. |
| `productSubscriptionOptions[].gracePeriodDayCount` | Integer | Any valid integer | The number of grace period days for the subscription. |
| `productSubscriptionOptions[].stripeXref` | String | Any valid string | The Stripe cross-reference (xref) for the subscription option. |
| `productSubscriptionOptions[].paypalXref` | String | Any valid string | The PayPal cross-reference (xref) for the subscription option. |
| `productUpgradeAssignments` | Array of Objects | - | Contains the upgrade assignments for the product. |
| `productUpgradeAssignments[].upgradeProductId` | Integer | Any valid product ID | The ID of the upgrade product. |
| `productResources` | Array of Objects | - | Contains the resources associated with the product. |
| `productResources[].id` | UUID | Any valid UUID | The ID of the resource. |
| `productResources[].name` | String | Any valid string | The name of the resource. |
| `productResources[].url` | String | Any valid URL | The URL of the resource. |
| `productResources[].fileId` | UUID | Any valid UUID | The ID of the file associated with the resource. |
| `productEvent` | Object | - | Contains information about the product event. |
| `productEvent.location` | String | `ToBeAnnounced` | The location of the product event. |
| `productEvent.link` | String | Any valid string | The link for the product event. |
| `productEvent.address` | Object | - | Contains the address of the product event. |
| `productEvent.address.streetAddress` | String | Any valid string | The street address of the event. |
| `productEvent.address.neighborhood` | String | Any valid string | The neighborhood of the event. |
| `productEvent.address.city` | String | Any valid string | The city of the event. |
| `productEvent.address.stateId` | String | Any valid state ID | The ID of the state for the event. |
| `productEvent.address.stateName` | String | Any valid string | The name of the state for the event. |
| `productEvent.address.zip` | String | Any valid zip code | The zip code for the event. |
| `productEvent.address.countryId` | String | Any valid country ID | The ID of the country for the event. |
| `productEvent.address.countryName` | String | Any valid string | The name of the country for the event. |
| `productEvent.date` | Date | Any valid date | The date of the product event. |
| `productEvent.time` | String | Any valid string | The time of the product event. |
| `productEvent.durationMinutes` | Integer | Any valid integer | The duration of the product event in minutes. |
| `productEvent.timezone` | String | Any valid string | The timezone of the product event. |
| `productEvent.languageId` | String | Any valid language ID | The ID of the language for the product event. |
***

**Request Body**

        {
        "code": "string",
        "name": "string",
        "description": "string",
        "descriptionHtml": "string",
        "groupId": 0,
        "groupName": "string",
        "type": "General",
        "price": 0,
        "currencyId": "string",
        "commissionableAmount": 0,
        "maxCommissionRate": 0,
        "maxCommissionRateTier2": 0,
        "unit": "Day",
        "stripeXref": "string",
        "paypalXref": "string",
        "downgradeProductId": 0,
        "isPublished": true,
        "publicName": "d.hNIhY186~l_taL1Bp39LH-jCo2Z0yzYsizqSb7CN0WkfcdqtAeqCULhGbtIp4snXV-_OKN1N.PmaRILE",
        "publishDate": "2024-04-29T04:13:55.190Z",
        "publicAllowCoupon": true,
        "createUser": true,
        "productServices": [
        {
                "memberServiceId": 0,
                "memberServiceLevelId": 0
        }
        ],
        "productSubscriptionOptions": [
        {
                "frequency": "Monthly",
                "signupFee": 0,
                "commissionableSignupFeeAmount": 0,
                "fee": 0,
                "commissionableFeeAmount": 0,
                "trialDayCount": 0,
                "customPeriodCount": 0,
                "customPeriodType": "Days",
                "cycles": 0,
                "gracePeriodDayCount": 0,
                "stripeXref": "string",
                "paypalXref": "string"
        }
        ],
        "productUpgradeAssignments": [
        {
                "upgradeProductId": 0
        }
        ],
        "productResources": [
        {
                "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                "name": "string",
                "url": "string",
                "fileId": "3fa85f64-5717-4562-b3fc-2c963f66afa6"
        }
        ],
        "productEvent": {
        "location": "ToBeAnnounced",
        "link": "string",
        "address": {
                "streetAddress": "string",
                "neighborhood": "string",
                "city": "string",
                "stateId": "str",
                "stateName": "string",
                "zip": "string",
                "countryId": "st",
                "countryName": "string"
        },
        "date": "2024-04-29T04:13:55.190Z",
        "time": "string",
        "durationMinutes": 0,
        "timezone": "string",
        "languageId": "st"
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

***

## UPDATE PRODUCT
Update a product 
***

'**PUT** {environment domain}/api/services/CRM/Product/UpdateProduct
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| connectedAccountId | String | Valid Stripe account ID | The unique identifier of the connected Stripe account, typically starting with "acct_" followed by alphanumeric characters |
***

**Response Body**

                {
        "id": 0,
        "code": "string",
        "name": "string",
        "description": "string",
        "descriptionHtml": "string",
        "groupId": 0,
        "groupName": "string",
        "type": "General",
        "price": 0,
        "currencyId": "string",
        "commissionableAmount": 0,
        "maxCommissionRate": 0,
        "maxCommissionRateTier2": 0,
        "unit": "Day",
        "stripeXref": "string",
        "paypalXref": "string",
        "downgradeProductId": 0,
        "isPublished": true,
        "publicName": "qf9aY",
        "publishDate": "2024-04-29T04:17:16.371Z",
        "publicAllowCoupon": true,
        "createUser": true,
        "productServices": [
        {
                "memberServiceId": 0,
                "memberServiceLevelId": 0
        }
        ],
        "productSubscriptionOptions": [
        {
                "frequency": "Monthly",
                "signupFee": 0,
                "commissionableSignupFeeAmount": 0,
                "fee": 0,
                "commissionableFeeAmount": 0,
                "trialDayCount": 0,
                "customPeriodCount": 0,
                "customPeriodType": "Days",
                "cycles": 0,
                "gracePeriodDayCount": 0,
                "stripeXref": "string",
                "paypalXref": "string"
        }
        ],
        "productUpgradeAssignments": [
        {
                "upgradeProductId": 0
        }
        ],
        "productResources": [
        {
                "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
                "name": "string",
                "url": "string",
                "fileId": "3fa85f64-5717-4562-b3fc-2c963f66afa6"
        }
        ],
        "productEvent": {
        "location": "ToBeAnnounced",
        "link": "string",
        "address": {
                "streetAddress": "string",
                "neighborhood": "string",
                "city": "string",
                "stateId": "str",
                "stateName": "string",
                "zip": "string",
                "countryId": "st",
                "countryName": "string"
        },
        "date": "2024-04-29T04:17:16.371Z",
        "time": "string",
        "durationMinutes": 0,
        "timezone": "string",
        "languageId": "st"
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

## LIST PRODUCTS
Retrieve a list of all products
***

'**GET** {environment domain}/api/services/CRM/Product/GetProducts?type={type}& currency_Id={currencyId}&onlyTenant={onlyTenant}
***

### Request Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
| --- | --- | --- | --- |
| `type` | String | `General`, `Subscription`, `Digital`, `Event` | The type of products to retrieve. |
| `currency_Id` | String | `USD`, `JPY`, `IND`, etc. | The currency ID to filter the products by. |
| `onlyTenant` | Boolean | `true`, `false` | Indicates whether to retrieve only products for the current tenant. |
        
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

## DELETE PRODUCT
Remove a product from the system using its ID
***

'**DELETE** {environment domain}/api/services/CRM/Product/DeleteProduct?id={{product_id}}
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| product_id | String | Any valid string | The id of the product |

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