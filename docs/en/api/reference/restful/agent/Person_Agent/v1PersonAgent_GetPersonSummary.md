---
title: POST Agents/Person/GetPersonSummary
uid: v1PersonAgent_GetPersonSummary
generated: true
---

# POST Agents/Person/GetPersonSummary

```http
POST /api/v1/Agents/Person/GetPersonSummary
```

Get summary of person and recent activity.







## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/Person/GetPersonSummary?$select=name,department,category/id
```


## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| Content-Type | Content-type of the request body: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/x-www-form-urlencoded`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept         | Content-type(s) you would like the response in: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept-Language | Convert string references and multi-language values into a specified language (iso2) code. |
| SO-Language | Convert string references and multi-language values into a specified language (iso2) code. Overrides Accept-Language value. |
| SO-Culture | Number, date formatting in a specified culture (iso2 language) code. Partially overrides SO-Language/Accept-Language value. Ignored if no Language set. |
| SO-TimeZone | Specify the timezone code that you would like date/time responses converted to. |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |

## Request Body: request 

PersonId, Limit 

| Property Name | Type |  Description |
|----------------|------|--------------|
| PersonId | Integer |  |
| Limit | Integer |  |

## Response:

OK

| Response | Description |
|----------------|-------------|
| 200 | OK |

### Response body: PersonSummary

| Property Name | Type |  Description |
|----------------|------|--------------|
| Person | Person | Simple Person data. |
| Tickets | array | Recent tickets on person |
| Followups | array | Recent follow-ups on person |
| Documents | array | Recent documents on person |
| Sales | array | Recent sales on person |
| Chats | array | Recent chats with person |

## Sample request

```http!
POST /api/v1/Agents/Person/GetPersonSummary
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: sv
Content-Type: application/json; charset=utf-8

{
  "PersonId": 454,
  "Limit": 354
}
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "Person": null,
  "Tickets": [
    {
      "TicketId": 555,
      "TicketStatus": 131,
      "Title": "nobis",
      "Registered": "2018-07-18T03:31:26.9174931+02:00",
      "IconHint": "et"
    },
    {
      "TicketId": 555,
      "TicketStatus": 131,
      "Title": "nobis",
      "Registered": "2018-07-18T03:31:26.9174931+02:00",
      "IconHint": "et"
    }
  ],
  "Followups": [
    {
      "AppointmentId": 418,
      "DocumentId": 356,
      "Date": "2005-08-13T03:31:26.9174931+02:00",
      "Description": "Polarised solution-oriented functionalities",
      "Completed": "Completed",
      "Registered": "2002-06-03T03:31:26.9174931+02:00"
    },
    {
      "AppointmentId": 418,
      "DocumentId": 356,
      "Date": "2005-08-13T03:31:26.9174931+02:00",
      "Description": "Polarised solution-oriented functionalities",
      "Completed": "Completed",
      "Registered": "2002-06-03T03:31:26.9174931+02:00"
    }
  ],
  "Documents": [
    {
      "AppointmentId": 290,
      "DocumentId": 658,
      "Date": "2000-01-13T03:31:26.9174931+01:00",
      "Description": "Focused user-facing extranet",
      "Completed": "Completed",
      "Registered": "2008-04-29T03:31:26.9174931+02:00"
    },
    {
      "AppointmentId": 290,
      "DocumentId": 658,
      "Date": "2000-01-13T03:31:26.9174931+01:00",
      "Description": "Focused user-facing extranet",
      "Completed": "Completed",
      "Registered": "2008-04-29T03:31:26.9174931+02:00"
    }
  ],
  "Sales": [
    {
      "SaleId": 166,
      "SaleDate": "2014-03-23T03:31:26.9174931+01:00",
      "Probability": 38,
      "Heading": "perspiciatis",
      "Amount": 25375.998,
      "Currency": "commodi",
      "AmountInBaseCurrency": 1469.846,
      "Status": "Lost",
      "Completed": "Completed",
      "Registered": "2017-06-05T03:31:26.9174931+02:00"
    }
  ],
  "Chats": [
    {
      "ChatSessionId": 64,
      "Name": "Kuphal Group",
      "CompanyName": "Swaniawski, McCullough and Medhurst",
      "FirstMessage": "nemo",
      "LastMessage": "adipisci",
      "WhenRequested": "2007-09-11T03:31:26.9174931+02:00",
      "WhenEnded": "2020-03-31T03:31:26.9174931+02:00"
    }
  ]
}
```