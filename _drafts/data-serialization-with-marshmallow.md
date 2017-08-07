---
layout: post
title:  "Data Serialization with Marshmallow"
date:   2017-08-07 07:40:59 -0400
categories: python marshmallow data serialization
---
# Data Serialization with Marshmallow

## What is Serialization

Serialization is the process of converting an instance of an object into a data that can be stored in memory and/or a database. That data can then be use to recreate the object at another time as needed. The process isn't always an one to one translation, but it is close enough to represent the original state of the information.

When reversing the process of serialization, it is called deserialization. You use stored data to reproduce an object so that it may be used again.

## What is Marshmallow

Marshmallow is a data serialization library for Python that handles incoming data from an internal or external source and converts it to a desired output.  It can perform validation and integrity checks on data based on a user defined schema.

Here is an example a schema:

Figure 1.1.1

```python
from marshmallow import Schema, fields

class EmployeeSchema(Schema):
    first_name = fields.String(required=True)
    last_name = fields.String(required=True)
    job_title = fields.String()
    company = fields.String(required=True)
```

The above schema can be used to make sure that a data passed through it has the fields `first_name`, `last_name`, `job_title`, and `company` which are all strings; all of which are strings. This ensures that if a company has a name like "123", it doesn't get used as an integer. `first_name`, `last_name`, and `company` are all required 

## Why use Marshmallow?

### User Defined Data Manipulation

Data comes from all kinds of sources and presented in many different forms. What determines the format of the data is the source it is coming from. The reason the data is delivered to users is dependent upon the developers who produced it. Data would then need to be manipulated to match desired usage would need manually.

This is where Marshmallow comes in. A developer can create schemata using Marshmallow that will ensure that requested data coming from the API is what they need it to be.  Marshmallow will makes sure that the requested data has the all variables necessary to proceed with processing and alter them into a format that can used by the developer if necessary.

### Resolve Different Naming Conventions

A very common difference between programming languages is the naming conventions for variables.

Here is an example of a JSON response generated with Javascript:

Figure 3.1.1

```json
{
   "firstName": "Brian",
   "LastName": "Rose",
   "jobTitle": "Junior Engineer",
   "company": "Croscon"
}

```

While there isn't anything wrong with the syntax, someone who uses Python might not like the fact that the variable names are camel cased and prefer snake case similar to the schema provided in Figure 1.1.1.

In this case, you can add an additional argument to the fields called `attribute` to handle the JSON variables and map it to correct schema variable.

Here is an example during the previous code from Figure 1.1.1:

Figure 3.1.2

```python
from marshmallow import fields, Schema

class EmployeeSchema(Schema):
    first_name = fields.String(required=True, attribute='firstName')
    last_name = fields.String(required=True, attribute='lastName')
    job_title = fields.String(attribute='jobTitle')
    company = fields.String(required=True)
```
