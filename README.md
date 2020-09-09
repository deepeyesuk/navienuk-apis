# Overview

This describes the resources that make up the Navien UK REST API v1. 
If you have any problems or requests, please contact [DEEPEYES App Support](app@deepeyes.co.uk).

All API access is over HTTPS, and all data is sent and received as JSON.

## Authentication

We use API key for authenticate the call. For the details, please contact [DEEPEYES App Support](app@deepeyes.co.uk).

Authentication header

```javascript
"x-api-key": "9c2kFTmLMKxxxxxxxxxx"
```

## APIs

### Update model and serial number mappings

Push all the model and serial number mappings

```bash
PUT /models
```

Example

```javascript
PUT /models
{
  [
    {
      "serial": "6662", 
      "modelName": "NCB 20 System"
    },
    {
      "serial": "0129", 
      "modelName": "NCB 28 Combi"
    },
    {
      "serial": "22418", 
      "modelName": "SmartPlus kit - Thermostat & Recevier"
    },
  ]
}
```

## Company

### Create or update a company

Create a new company with the company details

```bash
PUT /companies/:gas_safe_number
```

Example

```javascript
PUT /companies/207119
{
  "businessName": "All Gas services",
  "address": "The Panorama Park Street Ashford Kent",
  "postcode": "TN24 8DF",
  "phone": "+447956000000",
  "email": "info@email.com",
  "gasSafeNumber": "207119",
  "OftecNumber": "xxxx",
}
```

### Get the details of companies updated on the given date

```bash
GET /companies/dates/:todays_date
```

Example

```bash
GET /companies/20200908
```

Response

```javascript
{
  "companyName": "test company",
  ....
}
```


## Installer Users

### Get new installers registered on the given date

```bash
GET /users/dates/:todays_date
```

Example

```bash
GET /users/dates/20200908
```

Response

```javascript
{
  "familyName": "Test family name",
  ....
}
```

## Boiler registrations

### Get new registrations

```bash
GET /registrations/dates/:todays_date
```

Example

```bash
GET /registrations/dates/20200908
```

Response

```javascript
{
  ....
}
```

### Update Warranty

The Warranty API allows you to update the warranty year of an existing registration. 

```bash
PUT /registrations/:registrationId/warranty
```

#### Input
| Name | Type | Description |
| ---- | ---- | ----------- |
| `wrrantyYear` | `integer` | **Required** the warranty year value you want to set |

#### Example

```javascript
{
  "warrantyYear": 7
}
```


