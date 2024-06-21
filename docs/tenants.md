# TENANTS

## Add Tenants (1)

'**POST**  {environment domain}/api/services/CRM/Lead/SubmitTenancyRequest'

Submit the request for a new tenant to the system

### Request Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| companyName | String | Any valid string | Business Name from the first form |
| products | Array of Objects | See below | List of product subscription details |
| products[].productId | Integer | Valid product IDs | The platform ProductId |
| products[].paymentPeriodType | String | "Monthly", "Annual" | Subscription payment period |
| products[].quantity | Integer | 1 | Must be 1 for subscriptions |
| city | String | Any valid city name | City from "Tell Us About Yourself" form |
| state | String | Valid state/province codes | State from "Tell Us About Yourself" form |
| firstName | String | Any valid string | First Name from the first form |
| lastName | String | Any valid string | Last Name from the first form |
| email | String | Valid email address | Email from the first form |
| phone | String | "+[country code][number]" | Full phone number with country code |
| affiliateCode | String | Any valid string | Referral Code from the first form |

Optional parameters:

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| website | String | Valid URL | Will be stored as website link in Contact Details |
| stage | String | Valid stage names | The stage in which this lead will be added |
| tag | String | Any valid string | Tag to assign to this contact |
| phoneExt | String | Valid extension number | Phone extension (if applicable) |
| comments | String | Any text | Will be stored as a Lead Comment |
| sourceCode | String | Valid source codes | Tracking parameter for lead source |
| channelCode | String | Valid channel codes | Tracking parameter for lead channel |
| isHelpNeeded | Boolean | true/false | Indicates if help is needed (not required) |

**Request Body**

        {
        "companyName": "TestCRM", //Business Name from the first form
        "products": [
            {
            "productId": 318, // This is the platform ProductId be able to pass it here becuase products will be created before. 
            "paymentPeriodType": "Monthly", // We support several Periods.But on your form I saw 2 values: Monthly and Annual
            "quantity": 1 // must 1 becuase this is subscription
            }
        ],
        //"website"        : "www.Ajacco.com",         // It will be stored as website link in Contact Details
            "city"           : "Dallas",                 // City from "Tell Us About Yourself" form
            "state"          : "TX",                     // State from "Tell Us About Yourself" form
        //"stage"          : "Interested",             // You can set in which stage this lead will be added
        //"tag"            : "Partner Referral",       // You can assign any tag to this contact 
            "firstName"      : "John",                   // First Name from the first form
            "lastName"       : "Doe",                    // Last Name from the first form
            "email"          : "john.doe@testemail.com", // Email from the first form
            "phone"          : "+15059333763",           // Whole Phone number (with+ and country code) from "Tell Us About Yourself" form
        //"phoneExt"       : "665",                    // cab be skipped as you do not have it
        //"comments"       : "This Postman request",   // You can pass here any text. It will be stored as a Lead Comment
        //"sourceCode"     : "Manual",                 // This is tracking parameter which can be skipped if you do not use 
        //"channelCode"    : "Postman",                // This is tracking parameter which can be skipped if you do not use 
            "affiliateCode"  : "SomeCode"                // Referral Code from the first form
        //"isHelpNeeded"   : true                      // do not need

        }'/'''

**Request Body**
    {
    "companyName": "string",
    "products": [
        {
        "productId": 0,
        "paymentPeriodType": "Monthly",
        "quantity": 0
        }
    ],
    "couponCode": "string",
    "website": "string",
    "city": "}NLlplpNp}L{{Nlpp{pN{}l}p}p{pp'p''}'}pNL{LLlN-{lNN",
    "state": "hp",
    "stage": "string",
    "tag": "string",
    "utmParameter": {
        "source": "string",
        "medium": "string",
        "campaign": "string",
        "term": "string",
        "content": "string",
        "keyword": "string",
        "adGroup": "string",
        "name": "string"
    },
    "leadRequestXref": "string",
    "firstName": "string",
    "lastName": "string",
    "email": "73XduH5qK-Y#Nev+U&YDs$0k7lAqs4$Lko-d`-IblrU$oGnJ-KA'3/&rxXT~^G+TZl$Jk9T26d4GS$u|ys?hyH.iY~o'gI=5=x/F",
    "phone": "string",
    "phoneExt": "string",
    "comments": "string",
    "sourceCode": "string",
    "channelCode": "string",
    "campaignCode": "string",
    "affiliateCode": "string",
    "refererUrl": "string",
    "entryUrl": "string",
    "userAgent": "string",
    "clientIp": "string",
    "isHelpNeeded": true
    }/'''

**Sample Response: 200**
    {
    "leadRequestXref": "string",
    "contactId": 0
    }/'''


***
## Add Tenants (2)
Complete Tenant Registration
***

'**POST** {environment domain}/api/services/Platform/TenantSubscription/CompleteTenantRegistration
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| tenantName | String | Any valid string | Name of the Tenant. Can be Business Name from first or second form |
| adminPassword | String | Valid password string | Required. Can be password from the first form or autogenerated |
| companyName | String | Any valid string | Can be Business Name from first or second form |
| requestXref | String | Valid UUID | leadRequestXref parameter from SubmitTenancyRequest's output |
| returnBearerToken | Boolean | true/false | If true, BearerToken will be returned in output |

Optional parameters:

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| siteUrl | String | Valid URL | Optional URL for the tenant's site |
| tenancyName | String | Any valid string | Optional name for the tenancy |
***

**Response Body**

        {
            "tenantName": "Ajacco", //it will be used as Name of the Tenant. It can be Bussiness Name from first or the second form
            //"siteUrl": "", // optional
            "adminPassword": "Qq123456789", //Required. It can be password from the first form or autogenerateds
            //"tenancyName": "", // optional
            "companyName": "Ajacco",//It can be Bussiness Name from first or the second form
            "requestXref": "7244d39e-2b4c-444a-9237-25a8a502a42b",//leadRequestXref parameter from SubmitTenancyRequest's output
            "returnBearerToken": true// If true BearerToken will be returted in output. I think we will need this bearer to run requests unter the tenant
        }/'''
***

**Sample Request**
    curl -X 'POST' \
    'https://crm.upgrade.chat/api/services/Platform/TenantSubscription/CompleteTenantRegistration' \
    -H 'accept: application/json;odata.metadata=minimal;odata.streaming=true' \
    -H 'Content-Type: application/json;odata.metadata=minimal;odata.streaming=true' \
    -H 'Authorization: null' \
    -d '{
    "requestXref": "string",
    "tenancyName": "cg514QZFCmhBNILbzF",
    "tenantName": "string",
    "companyName": "string",
    "siteUrl": "string",
    "adminPassword": "string",
    "noWelcomeEmail": true,
    "returnBearerToken": true
    }'/'''

**Sample Response: 200**
    {
    "tenantId": 0,
    "tenancyName": "string",
    "name": "string",
    "userName": "string",
    "userId": 0,
    "emailAddress": "string",
    "isEmailConfirmationRequired": true,
    "loginLink": "string",
    "paymentLink": "string",
    "stripePayUrl": "string",
    "publicInvoiceId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "bearerAccessToken": "string",
    "bearerRefreshToken": "string"
    }/'''
***

## Generate API KEY
Create API key for tenant's account future actions 
***

'**POST** {environment domain}/api/services/Platform/ApiKey/Generate
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| name | String | Any valid string | A specific name for the API KEY |
| expirationDate | ISO 8601 date-time | Valid future date-time | The expiration time of the API KEY. The API KEY will cease to function after this time |
| userId | Integer | 0 or positive integer | Optional. CRM User ID. Can be provided to generate an API KEY for another user. If omitted, the API KEY will be generated for the currently logged-in user |
| paths | String | Comma-separated list of API method paths | Optional. A list of API methods can be specified here. If provided, the API KEY will only work for these specified API methods |
***

**Request Body**
    {
    "name": "string",
    "expirationDate": "2024-06-21T08:58:52.393Z",
    "userId": 0,
    "paths": "string"
    }/'''

**Sample Request**
        {
        "name": "string", // A certain name of the API KEY
        "expirationDate": "2023-12-12T16:40:40.016Z", // You have to set the expiration time of the API KEY. After this time API KEY will not work
        "userId": 0,// Optional. CRM User ID. It can be passed if you are going to generate API KEY for another user. Can be skipped then API KEY will be generated for user which is logged in
        "paths": "string" // Optional. Here the list of API methods can be set and this API KEY will work only for those API methods
        }/'''
***

**Sample Response: 200**
    {
    "id": 0,
    "name": "string",
    "key": "string",
    "expirationDate": "2024-06-21T08:58:52.395Z",
    "creationTime": "2024-06-21T08:58:52.395Z",
    "userId": 0,
    "userName": "string",
    "paths": "string"
    }/'''

***

## Link Tenants
Link multiple tenants
***

'**POST** {environment domain}/api/services/Platform/UserLink/LinkToUser
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| tenancyName | String | Any valid string | The name of the tenancy or organization to authenticate against |
| usernameOrEmailAddress | String | Valid username or email address | The username or email address of the user attempting to authenticate |
| password | String | Valid password string | The password associated with the provided username or email address |
***

**Response Body**
    {
    "tenancyName": "string",
    "usernameOrEmailAddress": "string",
    "password": "string"
    }/'''

**Sample Request**
    curl -X 'POST' \
    'https://crm.upgrade.chat/api/services/Platform/UserLink/LinkToUser' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json;odata.metadata=minimal;odata.streaming=true' \
    -H 'Authorization: null' \
    -d '{
    "tenancyName": "string",
    "usernameOrEmailAddress": "string",
    "password": "string"
    }'/'''
***

**Response: 200 (Success)**

***

## Delete Tenant
Delete Tenant
***

**DELETE** {environment domain}/api/services/Platform/Tenant/DeleteTenant?Id=tenant_id 

***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| tenant_id | String | Any valid string | The id of the tenant or organization to be deleted |
***

**Sample Request**
    curl -X 'DELETE' \
    'https://crm.upgrade.chat/api/services/Platform/Tenant/DeleteTenant' \
    -H 'accept: */*' \
    -H 'Authorization: Bearer <your token>'/'''
***

**Response: 200 (Success)**

***

## Update Tenant Account Currency
Update tenant account default currency.
***

'**PUT**  {environment domain}/api/services/Platform/TenantSettings/UpdateGeneralSettings
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| defaultCountryCode | String | Valid ISO 3166-1 alpha-2 country code | The default country code for the account, e.g., "US" for United States |
| timezone | String | Valid timezone string or empty | The timezone for the account. If left empty, a default may be used |
| timezoneForComparison | String | Valid timezone string | The timezone to be used for comparison purposes, e.g., "UTC" |
| zendeskAccountUrl | String | Valid URL or empty string | The URL for the associated Zendesk account, if applicable |
| publicPhone | String or null | Valid phone number or null | The public phone number for the account. Can be null if not provided |
| currency | String | Valid ISO 4217 currency code | The currency to be used for the account, e.g., "JPY" for Japanese Yen |
| publicSiteUrl | String or null | Valid URL or null | The public website URL for the account. Can be null if not provided |
***

**Response Body**
        {
            "defaultCountryCode": "US",
            "timezone": "",
            "timezoneForComparison": "UTC",
            "zendeskAccountUrl": "",
            "publicPhone": null,
            "currency": "JPY",
            "publicSiteUrl": null
        }/'''
***

**Sample Request**
    curl -X 'PUT' \
    'https://crm.upgrade.chat/api/services/Platform/TenantSettings/UpdateGeneralSettings' \
    -H 'accept: */*' \
    -H 'Content-Type: application/json;odata.metadata=minimal;odata.streaming=true' \
    -H 'Authorization: null' \
    -d '{
    "defaultCountryCode": "string",
    "timezone": "string",
    "timezoneForComparison": "string",
    "zendeskAccountUrl": "string",
    "publicPhone": "string",
    "currency": "string",
    "publicSiteUrl": "string"
    }'/'''
***

**Response: 200 (Sucess)**
***

## Get Tenant Account Login Link
Login user without entering email and password
***

'**GET** {environment domain}/api/services/Platform/User/GetAutoLoginLink?userId={user_id}&lifeTimeMinutes={minutes}
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| user_id | String | Any valid string | The id of the tenant or organization to be deleted |
| lifeTimeMinutes | String | Any valid string | The time in minutes |
***


**Sample Request**

curl -X 'GET' \
  'https://crm.upgrade.chat/api/services/Platform/User/GetAutoLoginLink' \
  -H 'accept: application/json;odata.metadata=minimal;odata.streaming=true' \
  -H 'Authorization: null'/'''
***

**Response: 200**

## Set Stripe Connected Account
Set already connected stripe account in the tenants account
***

'**POST** {environment domain}/api/services/CRM/TenantPaymentSettings/SetStripeConnectedAccount
***

### Request Parameters
| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| connectedAccountId | String | Valid Stripe account ID | The unique identifier of the connected Stripe account, typically starting with "acct_" followed by alphanumeric characters |
***

**Response Body**
{
  "connectedAccountId": "acct_1MD475HHdexuAbVt"

}

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

**Response: 200 (Success)**


***
