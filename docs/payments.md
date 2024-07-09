## ADD PAYMENTS
Add a new payment to the system and mark invoice as paid in the system
***

'**POST** {environment domain}/api/services/CRM/Invoice/AddBankCardPayment
***

### Request Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
| --- | --- | --- | --- |
| `invoiceNumber` | String | Any valid string | The invoice number for the payment. |
| `date` | Date | Any valid date | The date of the payment. |
| `orderStage` | String | `Draft`, `Pending`, `Complete`, `Cancelled`, `Refunded` | The stage of the order associated with the payment. |
| `amount` | Decimal | Any valid decimal number | The amount of the payment. A negative value indicates a refund. |
| `gatewayName` | String | Any valid string | The name of the payment gateway used for the transaction. |
| `gatewayTransactionId` | String | Any valid string | The transaction ID from the payment gateway. |
| `transactionType` | String | `Sale`, `Refund` | The type of the transaction. |
| `hasRecurringBilling` | Boolean | `true`, `false` | Indicates whether the payment is part of a recurring billing. |

***

**Request Body**

                {
        //"paymentId": 6822,
        "invoiceNumber": "{{invoiceNumber}}",
        "date": "{{date}}",
        "orderStage": "Complete",
        "amount": {{amount}}, // negative amount for Refund
        "gatewayName": "{{gatewayName}}",
        "gatewayTransactionId": "{{gatewayTransactionId}}",
        "transactionType": "Sale", // "Refund" should be passed for refund
        "hasRecurringBilling": false
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