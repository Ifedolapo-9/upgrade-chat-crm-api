# CUSTOMERS

The Tenants resource manages all aspects of tenant lifecycle within the Upgrade.chat multi-tenant system. It provides endpoints for tenant creation, registration, authentication, and configuration. Key features include:

- Two-step tenant creation process
- Tenant-specific authentication
- Account configuration (timezone, currency, contact info)
- API key management
- User management within tenants
- Integration with external services (e.g., Zendesk, Stripe)
- Subscription and product management

## ADD/UPDATE CUSTOMER

'**POST** {environment domain}/api/services/CRM/Contact/CreateOrUpdateContact'

Create or update leads, contacts, and customers

### Request Parameters

## Upgrade.chat API Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
| --- | --- | --- | --- |
| `matchExisting` | Boolean | `true`, `false` | Indicates whether to match the contact with an existing contact in the system. |
| `parentContactId` | Integer | Any valid contact ID | The ID of the parent contact, if the contact being created is a child contact. |
| `questionnaireAnswers` | Object | - | Contains information about the questionnaire and the questions and answers. |
| `questionnaireAnswers.questionnaire` | Object | - | Holds information about the questionnaire. |
| `questionnaireAnswers.questionnaire.xref` | String | Any valid string | The external reference (xref) of the questionnaire. |
| `questionnaireAnswers.questionnaire.name` | String | Any valid string | The name of the questionnaire. |
| `questionnaireAnswers.questionsAndAnswers` | Array of Objects | - | Contains the questions and answers. |
| `questionnaireAnswers.questionsAndAnswers[].question` | Object | - | Holds information about the question. |
| `questionnaireAnswers.questionsAndAnswers[].question.xref` | String | Any valid string | The external reference (xref) of the question. |
| `questionnaireAnswers.questionsAndAnswers[].question.type` | String | `QuestionWithOptions` | The type of the question. |
| `questionnaireAnswers.questionsAndAnswers[].question.text` | String | Any valid string | The text of the question. |
| `questionnaireAnswers.questionsAndAnswers[].question.sortOrder` | Integer | Any valid integer | The sort order of the question. |
| `questionnaireAnswers.questionsAndAnswers[].answers` | Array of Objects | - | Contains the answers to the question. |
| `questionnaireAnswers.questionsAndAnswers[].answers[].xref` | String | Any valid string | The external reference (xref) of the answer. |
| `questionnaireAnswers.questionsAndAnswers[].answers[].sortOrder` | Integer | Any valid integer | The sort order of the answer. |
| `questionnaireAnswers.questionsAndAnswers[].answers[].text` | String | Any valid string | The text of the answer. |
| `contactId` | Integer | Any valid contact ID | The ID of the contact. |
| `contactXRef` | String | Any valid string | The external reference (xref) of the contact. |
| `namePrefix` | String | Any valid string | The prefix of the contact's name. |
| `firstName` | String | Any valid string | The first name of the contact. |
| `middleName` | String | Any valid string | The middle name of the contact. |
| `lastName` | String | Any valid string | The last name of the contact. |
| `nameSuffix` | String | Any valid string | The suffix of the contact's name. |
| `nickName` | String | Any valid string | The nickname of the contact. |
| `emailAddresses` | Array of Objects | - | Contains the email addresses of the contact. |
| `emailAddresses[].contactId` | Integer | Any valid contact ID | The ID of the contact. |
| `emailAddresses[].emailAddress` | String | Any valid email address | The email address of the contact. |
| `emailAddresses[].isActive` | Boolean | `true`, `false` | Indicates whether the email address is active. |
| `emailAddresses[].isConfirmed` | Boolean | `true`, `false` | Indicates whether the email address is confirmed. |
| `emailAddresses[].comment` | String | Any valid string | A comment about the email address. |
| `emailAddresses[].usageTypeId` | String | Any valid usage type ID | The ID of the usage type for the email address. |
| `phoneNumbers` | Array of Objects | - | Contains the phone numbers of the contact. |
| `phoneNumbers[].contactId` | Integer | Any valid contact ID | The ID of the contact. |
| `phoneNumbers[].phoneNumber` | String | Any valid phone number | The phone number of the contact. |
| `phoneNumbers[].phoneExtension` | String | Any valid string | The phone extension of the contact. |
| `phoneNumbers[].isActive` | Boolean | `true`, `false` | Indicates whether the phone number is active. |
| `phoneNumbers[].isConfirmed` | Boolean | `true`, `false` | Indicates whether the phone number is confirmed. |
| `phoneNumbers[].comment` | String | Any valid string | A comment about the phone number. |
| `phoneNumbers[].usageTypeId` | String | Any valid usage type ID | The ID of the usage type for the phone number. |
| `addresses` | Array of Objects | - | Contains the addresses of the contact. |
| `addresses[].contactId` | Integer | Any valid contact ID | The ID of the contact. |
| `addresses[].startDate` | Date | Any valid date | The start date of the address. |
| `addresses[].endDate` | Date | Any valid date | The end date of the address. |
| `addresses[].isActive` | Boolean | `true`, `false` | Indicates whether the address is active. |
| `addresses[].isConfirmed` | Boolean | `true`, `false` | Indicates whether the address is confirmed. |
| `addresses[].usageTypeId` | String | Any valid usage type ID | The ID of the usage type for the address. |
| `addresses[].ownershipTypeId` | String | Any valid ownership type ID | The ID of the ownership type for the address. |
| `addresses[].streetAddress` | String | Any valid string | The street address. |
| `addresses[].neighborhood` | String | Any valid string | The neighborhood. |
| `addresses[].city` | String | Any valid string | The city. |
| `addresses[].stateId` | String | Any valid state ID | The ID of the state. |
| `addresses[].stateName` | String | Any valid string | The name of the state. |
| `addresses[].zip` | String | Any valid zip code | The zip code. |
| `addresses[].countryId` | String | Any valid country ID | The ID of the country. |
| `addresses[].countryName` | String | Any valid string | The name of the country. |
| `addresses[].comment` | String | Any valid string | A comment about the address. |
| `links` | Array of Objects | - | Contains the links associated with the contact. |
| `links[].contactId` | Integer | Any valid contact ID | The ID of the contact. |
| `links[].isConfirmed` | Boolean | `true`, `false` | Indicates whether the link is confirmed. |
| `links[].isCompany` | Boolean | `true`, `false` | Indicates whether the link is to a company. |
| `links[].url` | String | Any valid URL | The URL of the link. |
| `links[].isActive` | Boolean | `true`, `false` | Indicates whether the link is active. |
| `links[].comment` | String | Any valid string | A comment about the link. |
| `links[].linkTypeId` | String | Any valid link type ID | The ID of the link type. |
| `dob` | Date | Any valid date | The date of birth of the contact. |
| `bankCode` | String | Any valid string | The bank code of the contact. |
| `bankCodeSource` | String | Any valid string | The source of the bank code. |
| `gender` | String | `Female`, `Male`, `Other` | The gender of the contact. |
| `experience` | String | Any valid string | The experience of the contact. |
| `profileSummary` | String | Any valid string | The profile summary of the contact. |
| `note` | String | Any valid string | A note about the contact. |
| `interests` | Array of Strings | Any valid strings | The interests of the contact. |
| `companyName` | String | Any valid string | The name of the company. |
| `industry` | String | Any valid string | The industry of the company. |
| `photo` | Object | - | Contains information about the contact's photo. |
| `photo.original` | String | Any valid string | The URL of the original photo. |
| `photo.thumbnail` | String | Any valid string | The URL of the thumbnail photo. |
| `photo.source` | String | Any valid string | The source of the photo. |
| `photo.comment` | String | Any valid string | A comment about the photo. |
| `sourceContactId` | Integer | Any valid contact ID | The ID of the source contact. |
| `sourceOrganizationUnitId` | Integer | Any valid organization unit ID | The ID of the source organization unit. |
| `personAffiliateCode` | String | Any valid string | The affiliate code of the person. |
| `title` | String | Any valid string | The title of the contact. |
| `tags` | Array of Objects | - | Contains the tags associated with the contact. |
| `tags[].name` | String | Any valid string | The name of the tag. |
| `lists` | Array of Objects | - | Contains the lists associated with the contact. |
| `lists[].name` | String | Any valid string | The name of the list. |
| `assignedUserId` | Integer | Any valid user ID | The ID of the user the contact is assigned to. |
| `ratingId` | Integer | Any valid rating ID | The ID of the rating for the contact. |
| `preferredLanguageCode` | String | Any valid language code | The preferred language code of the contact. |
| `contactGroupId` | String | Any valid contact group ID | The ID of the contact group. |
| `isActive` | Boolean | `true`, `false` | Indicates whether the contact is active. |
| `isProspective` | Boolean | `true`, `false` | Indicates whether the contact is a prospective customer. |
| `partnerTypeName` | String | Any valid string | The name of the partner type. |
| `leadTypeId` | Integer | Any valid lead type ID | The ID of the lead type. |
| `leadTypeSysId` | String | Any valid string | The system ID of the lead type. |
| `stageId` | Integer | Any valid stage ID | The ID of the stage. |
| `dealAmount` | Decimal | Any valid decimal number | The deal amount. |
| `currencyId` | String | Any valid currency ID | The ID of the currency. |
| `installmentAmount` | Decimal | Any valid decimal number | The installment amount. |
| `followUpDate` | Date | Any valid date | The follow-up date. |
| `trackingInfo` | Object | - | Contains information about the tracking of the contact. |
| `trackingInfo.sourceCode` | String | Any valid string | The source code. |
| `trackingInfo.channelCode` | String | Any valid string | The channel code. |
| `trackingInfo.campaignCode` | String | Any valid string | The campaign code. |
| `trackingInfo.affiliateCode` | String | Any valid string | The affiliate code. |
| `trackingInfo.refererUrl` | String | Any valid URL | The referrer URL. |
| `trackingInfo.entryUrl` | String | Any valid URL | The entry URL. |
| `trackingInfo.userAgent` | String | Any valid string | The user agent. |
| `trackingInfo.clientIp` | String | Any valid IP address | The client IP address. |
| `trackingInfo.siteUrl` | String | Any valid URL | The site URL. |
| `trackingInfo.comments` | String | Any valid string | Comments about the tracking. |
| `trackingInfo.customField1` | String | Any valid string | Custom field 1. |
| `trackingInfo.customField2` | String | Any valid string | Custom field 2. |
| `trackingInfo.customField3` | String | Any valid string | Custom field 3. |
| `trackingInfo.customField4` | String | Any valid string | Custom field 4. |
| `trackingInfo.customField5` | String | Any valid string | Custom field 5. |
| `utmParameter` | Object | - | Contains information about the UTM parameters. |
| `utmParameter.source` | String | Any valid string | The UTM source. |
| `utmParameter.medium` | String | Any valid string | The UTM medium. |
| `utmParameter.campaign` | String | Any valid string | The UTM campaign. |
| `utmParameter.term` | String | Any valid string | The UTM term. |
| `utmParameter.content` | String | Any valid string | The UTM content. |
| `utmParameter.keyword` | String | Any valid string | The UTM keyword. |
| `utmParameter.adGroup` | String | Any valid string | The UTM ad group. |
| `utmParameter.name` | String | Any valid string | The UTM name. |
| `inviteUser` | Boolean | `true`, `false` | Indicates whether to invite the user. |
| `generateAutoLoginLink` | Boolean | `true`, `false` | Indicates whether to generate an auto-login link. |
| `newUserPassword` | String | Any valid string | The password for the new user. |
| `changeNewUserPasswordOnNextLogin` | Boolean | `true`, `false` | Indicates whether the new user should change the password on the next login. |
| `noWelcomeEmail` | Boolean | `true`, `false` | Indicates whether to skip sending the welcome email. |
| `welcomeEmailTemplateRef` | String | Any valid string | The reference to the welcome email template. |
| `propertyInfo` | Object | - | Contains information about the property. |
| `propertyInfo.propertyId` | Integer | Any valid property ID | The ID of the property. |
| `propertyInfo.name` | String | Any valid string | The name of the property. |
| `propertyInfo.address` | Object | - | Contains the address of the property. |
| `propertyInfo.address.contactId` | Integer | Any valid contact ID | The ID of the contact. |
| `propertyInfo.address.startDate` | Date | Any valid date | The start date of the address. |
| `propertyInfo.address.endDate` | Date | Any valid date | The end date of the address. |
| `propertyInfo.address.isActive` | Boolean | `true`, `false` | Indicates whether the address is active. |
| `propertyInfo.address.isConfirmed` | Boolean | `true`, `false` | Indicates whether the address is confirmed. |
| `propertyInfo.address.usageTypeId` | String | Any valid usage type ID | The ID of the usage type for the address. |
| `propertyInfo.address.ownershipTypeId` | String | Any valid ownership type ID | The ID of the ownership type for the address. |
| `propertyInfo.address.streetAddress` | String | Any valid string | The street address. |
| `propertyInfo.address.neighborhood` | String | Any valid string | The neighborhood. |
| `propertyInfo.address.city` | String | Any valid string | The city. |
| `propertyInfo.address.stateId` | String | Any valid state ID | The ID of the state. |
| `propertyInfo.address.stateName` | String | Any valid string | The name of the state. |
| `propertyInfo.address.zip` | String | Any valid zip code | The zip code. |
| `propertyInfo.address.countryId` | String | Any valid country ID | The ID of the country. |
| `propertyInfo.address.countryName` | String | Any valid string | The name of the country. |
| `propertyInfo.address.comment` | String | Any valid string | A comment about the address. |
| `propertyInfo.note` | String | Any valid string | A note about the property. |
| `bypassValidation` | Boolean | `true`, `false` | Indicates whether to bypass validation. |
***

**Request Body**

        {
        "matchExisting": true,
        "parentContactId": 0,
        "questionnaireAnswers": {
            "questionnaire": {
            "xref": "string",
            "name": "string"
            },
            "questionsAndAnswers": [
            {
                "question": {
                "xref": "string",
                "type": "QuestionWithOptions",
                "text": "string",
                "sortOrder": 0
                },
                "answers": [
                {
                    "xref": "string",
                    "sortOrder": 0,
                    "text": "string"
                }
                ]
            }
            ]
        },
        "contactId": 0,
        "contactXRef": "string",
        "namePrefix": "string",
        "firstName": "string",
        "middleName": "string",
        "lastName": "string",
        "nameSuffix": "string",
        "nickName": "string",
        "emailAddresses": [
            {
            "contactId": 0,
            "emailAddress": "string",
            "isActive": true,
            "isConfirmed": true,
            "comment": "string",
            "usageTypeId": "string"
            }
        ],
        "phoneNumbers": [
            {
            "contactId": 0,
            "phoneNumber": "string",
            "phoneExtension": "string",
            "isActive": true,
            "isConfirmed": true,
            "comment": "string",
            "usageTypeId": "string"
            }
        ],
        "addresses": [
            {
            "contactId": 0,
            "startDate": "2024-04-29",
            "endDate": "2024-04-29",
            "isActive": true,
            "isConfirmed": true,
            "usageTypeId": "string",
            "ownershipTypeId": "string",
            "streetAddress": "string",
            "neighborhood": "string",
            "city": "string",
            "stateId": "string",
            "stateName": "string",
            "zip": "string",
            "countryId": "string",
            "countryName": "string",
            "comment": "string"
            }
        ],
        "links": [
            {
            "contactId": 0,
            "isConfirmed": true,
            "isCompany": true,
            "url": "string",
            "isActive": true,
            "comment": "string",
            "linkTypeId": "string"
            }
        ],
        "dob": "2024-04-29T04:25:54.857Z",
        "bankCode": "stri",
        "bankCodeSource": "string",
        "gender": "Female",
        "experience": "string",
        "profileSummary": "string",
        "note": "string",
        "interests": [
            "string"
        ],
        "companyName": "string",
        "industry": "string",
        "photo": {
            "original": "string",
            "thumbnail": "string",
            "source": "string",
            "comment": "string"
        },
        "sourceContactId": 0,
        "sourceOrganizationUnitId": 0,
        "personAffiliateCode": "string",
        "title": "string",
        "tags": [
            {
            "name": "string"
            }
        ],
        "lists": [
            {
            "name": "string"
            }
        ],
        "assignedUserId": 0,
        "ratingId": 0,
        "preferredLanguageCode": "string",
        "contactGroupId": "s",
        "isActive": true,
        "isProspective": true,
        "partnerTypeName": "string",
        "leadTypeId": 0,
        "leadTypeSysId": "string",
        "stageId": 0,
        "dealAmount": 0,
        "currencyId": "string",
        "installmentAmount": 0,
        "followUpDate": "2024-04-29T04:25:54.857Z",
        "trackingInfo": {
            "sourceCode": "string",
            "channelCode": "string",
            "campaignCode": "string",
            "affiliateCode": "string",
            "refererUrl": "string",
            "entryUrl": "string",
            "userAgent": "string",
            "clientIp": "string",
            "siteUrl": "string",
            "comments": "string",
            "customField1": "string",
            "customField2": "string",
            "customField3": "string",
            "customField4": "string",
            "customField5": "string"
        },
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
        "inviteUser": true,
        "generateAutoLoginLink": true,
        "newUserPassword": "string",
        "changeNewUserPasswordOnNextLogin": true,
        "noWelcomeEmail": true,
        "welcomeEmailTemplateRef": "string",
        "propertyInfo": {
            "propertyId": 0,
            "name": "string",
            "address": {
            "contactId": 0,
            "startDate": "2024-04-29",
            "endDate": "2024-04-29",
            "isActive": true,
            "isConfirmed": true,
            "usageTypeId": "string",
            "ownershipTypeId": "string",
            "streetAddress": "string",
            "neighborhood": "string",
            "city": "string",
            "stateId": "string",
            "stateName": "string",
            "zip": "string",
            "countryId": "string",
            "countryName": "string",
            "comment": "string"
            },
            "note": "string"
        },
        "bypassValidation": true
        }
 

**Sample Request**

        curl -X 'POST' \
        'https://betacrm.upgrade.chat/api/services/CRM/Lead/SubmitTenancyRequest' \
        -H 'accept: application/json;odata.metadata=minimal;odata.streaming=true' \
        -H 'Content-Type: application/json;odata.metadata=minimal;odata.streaming=true' \
        -H 'Authorization: Bearer <your key>' \
        -d '{
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
        "city": "lpl'\''pN'\''}'\''N'\''L}L'\''{}pl{lLll'\''{pp{N'\''llN}L}{}L}{'\''Llp{pNp",
        "state": "ab",
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
        "email": "8BOXja9E}L7!w/pKMr?qFiJB+xaD2.$?76h?zc_wVAo.n=%a+4#|_mvyW*zX^.EyHgBu!Tv*aszZd5tU$L*tSIHMTkv1qQ+NJG+D",
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
        }'

**Sample Response: 200 (Success)**

        {
        "leadRequestXref": "string",
        "contactId": 0
        }


***

## GET CUSTOMER

'**GET** {environment domain}/api/services/CRM/Contact/GetContactInfo?id=contact_id'

Get customer information

### Request Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| contact_id | String | Any valid string | The id of contact |
***

**Sample Request**

        curl -X 'POST' \
        'https://betacrm.upgrade.chat/api/services/CRM/Lead/SubmitTenancyRequest' \
        -H 'accept: application/json;odata.metadata=minimal;odata.streaming=true' \
        -H 'Content-Type: application/json;odata.metadata=minimal;odata.streaming=true' \
        -H 'Authorization: Bearer <your key>' \
        -d '{
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
        "city": "lpl'\''pN'\''}'\''N'\''L}L'\''{}pl{lLll'\''{pp{N'\''llN}L}{}L}{'\''Llp{pNp",
        "state": "ab",
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
        "email": "8BOXja9E}L7!w/pKMr?qFiJB+xaD2.$?76h?zc_wVAo.n=%a+4#|_mvyW*zX^.EyHgBu!Tv*aszZd5tU$L*tSIHMTkv1qQ+NJG+D",
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
        }'

**Response: 200 (Success)**

***

## DELETE CUSTOMER

'**DELETE** {environment domain}/api/services/CRM/Contact/DeleteContact?id=customer_id'

Delete customer information

### Request Parameters

| FIELD NAME | FORMAT | VALID VALUES | DESCRIPTION |
|------------|--------|--------------|-------------|
| customer_id | String | Any valid string | The id of the customer |

***

**Sample Request**

        curl -X 'POST' \
        'https://betacrm.upgrade.chat/api/services/CRM/Lead/SubmitTenancyRequest' \
        -H 'accept: application/json;odata.metadata=minimal;odata.streaming=true' \
        -H 'Content-Type: application/json;odata.metadata=minimal;odata.streaming=true' \
        -H 'Authorization: Bearer <your key>' \
        -d '{
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
        "city": "lpl'\''pN'\''}'\''N'\''L}L'\''{}pl{lLll'\''{pp{N'\''llN}L}{}L}{'\''Llp{pNp",
        "state": "ab",
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
        "email": "8BOXja9E}L7!w/pKMr?qFiJB+xaD2.$?76h?zc_wVAo.n=%a+4#|_mvyW*zX^.EyHgBu!Tv*aszZd5tU$L*tSIHMTkv1qQ+NJG+D",
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
        }'

**Sample Response: 200 (Success)**

        {
        "leadRequestXref": "string",
        "contactId": 0
        }


***
