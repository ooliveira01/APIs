---
# NOTICE: Copyright 2024 Talend SA, Talend, Inc., and affiliates. All Rights Reserved. Customer’s use of the software contained herein is subject to the terms and conditions of the Agreement between Customer and Talend.
layout: "apiDefinition_1.1.0"
api-definition:
  specVersion: "4.1.0"
  info:
    name: "Contacts API"
    version: "4.1.0"
    description: "An API for keeping track of your contacts and the companies they work for."
    license: {}
    contact: {}
    termsOfService: ""
  contract:
    mediaTypes:
    - "application/json"
    sections:
    - name: "General"
      elementOrder:
      - "#/contract/texts/76415f4b-8a2c-4842-8321-92724900907c"
      - "#/contract/texts/e761f684-32c9-4881-945f-ab24db5f0e1f"
      - "#/contract/types/88fc9d36-2692-44a1-8c9b-5429bc8fab98"
    - name: "Contacts"
      description: ""
      elementOrder:
      - "#/contract/resources/589bce4d-dae8-40da-a811-6218e53ed8de"
      - "#/contract/resources/17e86470-f6ff-4aa0-8abe-eca757f9cf78"
      - "#/contract/types/a7f2f161-5a8e-4a02-8199-6833ad1dbdd6"
    - name: "Companies"
      elementOrder:
      - "#/contract/resources/ec07d97f-a2c4-48eb-9a60-7a309b067b3a"
      - "#/contract/resources/e99d8d0e-2acd-41e9-bf0b-51650c7a7128"
      - "#/contract/types/29cfc35d-5765-4775-8b4c-d9f9968d6307"
    securitySchemes:
      "56f788ca-2ee8-4b6f-9e51-da9f22102bac":
        name: "HTTP_BASIC"
        type: "basic"
        description: "All GET methods are public, meaning that *you can read all the data*. Write operations require authentication and therefore are forbidden to the general public."
        describedBy: {}
    resources:
      ec07d97f-a2c4-48eb-9a60-7a309b067b3a:
        path: "/companies/"
        section: "#/contract/sections/f99f937f-a232-4513-b133-3ad59b59da38"
        operations:
          "53f1cb6b-94c8-4dc9-af1b-4289ed1365a4":
            name: "Load the list of Companies"
            method: "GET"
            description: "Loads a list of Company"
            tags:
            - "Companies"
            queryParameters:
            - type: "#/components/queryParameters/7160507d-7112-4717-88e3-e64c16a47654"
            - type: "#/components/queryParameters/b931de52-3eeb-47c0-81a9-693f6c6a504c"
            - type: "#/components/queryParameters/5b4bd8e1-5e73-4e7f-a671-7c31ea287d33"
            - name: "name"
              type: "STRING"
              description: "Allows to filter the collection of results by the value of field `name`"
              examples:
              - value: "George Street Brewery"
            responses:
              a44d611f-7e58-4536-8507-d219de8c2163:
                status: "200"
                description: "Status 200"
                headers:
                - type: "#/components/headers/586c6ef9-1ed7-4770-9f51-1e522061d2a8"
                - type: "#/components/headers/50aa2973-07c5-45be-960e-b53f8751b1e9"
                - type: "#/components/headers/8f2a1ed8-7a2f-4c89-ba15-b05c7bc29ae2"
                - type: "#/components/headers/7b587c76-48da-49bb-a9d7-924e450932f9"
                bodies:
                - type: "ARRAY"
                  items:
                    type: "#/contract/types/29cfc35d-5765-4775-8b4c-d9f9968d6307"
                  examples:
                  - value: |-
                      [{
                        "id": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f",
                        "name": "George Street Brewery",
                        "address":{
                          "street": "2 place de la Defense",
                          "zipcode": "92053",
                          "city": "Paris"
                        },
                        "tags":[
                          "brewery",
                          "beer",
                          "ale"
                        ]
                      }]
              "0b028cca-a82e-4751-a80b-0d90fca53235":
                status: "400"
                componentName: "Status 400"
                reference: "#/components/responses/a0f2f195-3599-4227-a9a0-495422576efe"
          "911f688c-17e9-4d5b-b5f8-d925be90db2a":
            name: "Create a new Company"
            method: "POST"
            description: "Adds a Company"
            tags:
            - "Companies"
            securedBy:
            - scheme: "#/contract/securitySchemes/56f788ca-2ee8-4b6f-9e51-da9f22102bac"
              scopes: []
            bodies:
            - type: "#/contract/types/29cfc35d-5765-4775-8b4c-d9f9968d6307"
              examples:
              - value: |-
                  {
                    "name": "George Street Brewery",
                    "address":{
                      "street": "2 place de la Defense",
                      "zipcode": "92053",
                      "city": "Paris"
                    },
                    "tags":[
                      "brewery",
                      "beer",
                      "ale"
                    ]
                  }
            responses:
              f108bf03-9d81-44fd-90a7-ab2064fff7a0:
                status: "200"
                description: "Status 200"
                bodies:
                - type: "#/contract/types/29cfc35d-5765-4775-8b4c-d9f9968d6307"
                  examples:
                  - value: |-
                      {
                        "id": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f",
                        "name": "George Street Brewery",
                        "address":{
                          "street": "2 place de la Defense",
                          "zipcode": "92053",
                          "city": "Paris"
                        },
                        "tags":[
                          "brewery",
                          "beer",
                          "ale"
                        ]
                      }
      e99d8d0e-2acd-41e9-bf0b-51650c7a7128:
        path: "/companies/{companyid}"
        section: "#/contract/sections/f99f937f-a232-4513-b133-3ad59b59da38"
        pathVariables:
        - type: "#/components/pathVariables/6dc2cfe5-a655-4b92-b0eb-0c3bfcc2e8c2"
        operations:
          "28030be1-158e-496c-bd7d-796a45a04c19":
            name: "Load a Company"
            method: "GET"
            description: "Loads a Company"
            tags:
            - "Companies"
            responses:
              "8e5c7bf4-7b83-491c-8825-c3461a0c4915":
                status: "200"
                description: "Status 200"
                bodies:
                - type: "#/contract/types/29cfc35d-5765-4775-8b4c-d9f9968d6307"
                  examples:
                  - value: |-
                      {
                        "id": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f",
                        "name": "George Street Brewery",
                        "address":{
                          "street": "2 place de la Defense",
                          "zipcode": "92053",
                          "city": "Paris"
                        },
                        "tags":[
                          "brewery",
                          "beer",
                          "ale"
                        ]
                      }
              b367ef16-69ff-4893-98e6-4d2ff4b2f545:
                status: "400"
                componentName: "Status 400"
                reference: "#/components/responses/a0f2f195-3599-4227-a9a0-495422576efe"
          "03e04a76-ac15-44ca-b7cf-0d3c8bb90936":
            name: "Update a Company"
            method: "PUT"
            description: "Updates a Company"
            tags:
            - "Companies"
            securedBy:
            - scheme: "#/contract/securitySchemes/56f788ca-2ee8-4b6f-9e51-da9f22102bac"
              scopes: []
            bodies:
            - type: "#/contract/types/29cfc35d-5765-4775-8b4c-d9f9968d6307"
              examples:
              - value: |-
                  {
                    "name": "George Street Brewery",
                    "address":{
                      "street": "2 place de la Defense",
                      "zipcode": "92053",
                      "city": "Paris"
                    },
                    "tags":[
                      "brewery",
                      "beer",
                      "ale"
                    ]
                  }
            responses:
              f4d9f294-7233-487c-a51f-790718321646:
                status: "200"
                description: "Status 200"
                bodies:
                - type: "#/contract/types/29cfc35d-5765-4775-8b4c-d9f9968d6307"
                  examples:
                  - value: |-
                      {
                        "id": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f",
                        "name": "George Street Brewery",
                        "address":{
                          "street": "2 place de la Defense",
                          "zipcode": "92053",
                          "city": "Paris"
                        },
                        "tags":[
                          "brewery",
                          "beer",
                          "ale"
                        ]
                      }
          e8cce56b-3868-475d-b18d-5d2688603820:
            name: "Delete a Company"
            method: "DELETE"
            description: "Deletes a Company"
            tags:
            - "Companies"
            securedBy:
            - scheme: "#/contract/securitySchemes/56f788ca-2ee8-4b6f-9e51-da9f22102bac"
              scopes: []
            responses:
              "9c65efd6-f426-4f88-af3a-339f8b021352":
                status: "200"
                description: "Status 200"
      "589bce4d-dae8-40da-a811-6218e53ed8de":
        path: "/contacts/"
        section: "#/contract/sections/7ea96dc3-52a9-4133-bccc-859625c568a9"
        operations:
          a72bbf0f-43b7-4c30-a35f-b4ceb2fdf349:
            name: "Get the list of Contacts"
            method: "GET"
            description: "Loads a list of Contact"
            tags:
            - "Contacts"
            queryParameters:
            - type: "#/components/queryParameters/7160507d-7112-4717-88e3-e64c16a47654"
            - type: "#/components/queryParameters/b931de52-3eeb-47c0-81a9-693f6c6a504c"
            - type: "#/components/queryParameters/5b4bd8e1-5e73-4e7f-a671-7c31ea287d33"
            - name: "firstName"
              type: "STRING"
              description: "Allows to filter the collection of results by the value of field `firstName`"
              examples:
              - value: "John"
            - name: "lastName"
              type: "STRING"
              description: "Allows to filter the collection of results by the value of field `lastName`"
              examples:
              - value: "Doe"
            - name: "active"
              type: "BOOLEAN"
              description: "Allows to filter the collection of results by the value of field `active`"
              examples:
              - value: true
              - value: false
            - name: "company"
              type: "STRING"
              description: "Allows to filter the collection of results by the value of field `company`"
              examples:
              - value: "0e8c9fb0-ad98-11e6-bf2e-47644ada7c0f"
            responses:
              c3965b5e-60de-4280-8867-3048fbc62623:
                status: "200"
                description: "Status 200"
                headers:
                - type: "#/components/headers/586c6ef9-1ed7-4770-9f51-1e522061d2a8"
                - type: "#/components/headers/50aa2973-07c5-45be-960e-b53f8751b1e9"
                - type: "#/components/headers/8f2a1ed8-7a2f-4c89-ba15-b05c7bc29ae2"
                - type: "#/components/headers/7b587c76-48da-49bb-a9d7-924e450932f9"
                bodies:
                - type: "ARRAY"
                  items:
                    type: "#/contract/types/a7f2f161-5a8e-4a02-8199-6833ad1dbdd6"
                  examples:
                  - value: |-
                      [{
                        "id": "0e8dd830-ad98-11e6-bf2e-47644ada7c0f",
                        "firstName": "John",
                        "lastName": "Smith",
                        "birthday": 152755200000,
                        "active": true,
                        "rank": 1,
                        "company": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f"
                      }]
              "89049d11-0d56-4e3c-afe8-b94802b09a2e":
                status: "400"
                componentName: "Status 400"
                reference: "#/components/responses/a0f2f195-3599-4227-a9a0-495422576efe"
          "9a642024-7464-4956-a3d2-8294ef3cb0a1":
            name: "Create a Contact"
            method: "POST"
            description: "Adds a Contact"
            tags:
            - "Contacts"
            securedBy:
            - scheme: "#/contract/securitySchemes/56f788ca-2ee8-4b6f-9e51-da9f22102bac"
              scopes: []
            bodies:
            - type: "#/contract/types/a7f2f161-5a8e-4a02-8199-6833ad1dbdd6"
              examples:
              - value: |-
                  {
                    "firstName": "John",
                    "lastName": "Smith",
                    "birthday": 152755200000,
                    "active": true,
                    "rank": 1,
                    "company": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f"
                  }
            responses:
              "9e53e7f3-3c5b-4fc4-805a-06b531058059":
                status: "200"
                description: "Status 200"
                bodies:
                - type: "#/contract/types/a7f2f161-5a8e-4a02-8199-6833ad1dbdd6"
                  examples:
                  - value: |-
                      {
                        "id": "0e8dd830-ad98-11e6-bf2e-47644ada7c0f",
                        "firstName": "John",
                        "lastName": "Smith",
                        "birthday": 152755200000,
                        "active": true,
                        "rank": 1,
                        "company": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f"
                      }
      "17e86470-f6ff-4aa0-8abe-eca757f9cf78":
        path: "/contacts/{contactid}"
        section: "#/contract/sections/7ea96dc3-52a9-4133-bccc-859625c568a9"
        pathVariables:
        - type: "#/components/pathVariables/238bfd13-9110-4da8-8d30-5eac4e67b88f"
        operations:
          c29715de-044b-4978-90d8-120ff4f2dee9:
            name: "Load a Contact"
            method: "GET"
            description: "Loads a Contact"
            tags:
            - "Contacts"
            responses:
              "1bc9bddc-a37f-4752-8ba0-9b672c1f3e79":
                status: "200"
                description: "Status 200"
                bodies:
                - type: "#/contract/types/a7f2f161-5a8e-4a02-8199-6833ad1dbdd6"
                  examples:
                  - value: |-
                      {
                        "id": "0e8dd830-ad98-11e6-bf2e-47644ada7c0f",
                        "firstName": "John",
                        "lastName": "Smith",
                        "birthday": 152755200000,
                        "active": true,
                        "rank": 1,
                        "company": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f"
                      }
              "340f305c-1e4f-455f-aa44-c57837f6d95e":
                status: "400"
                componentName: "Status 400"
                reference: "#/components/responses/a0f2f195-3599-4227-a9a0-495422576efe"
          "91b8076b-f416-4ebf-bc09-1cf615a3cbe2":
            name: "Update a Contact"
            method: "PUT"
            description: "Updates a Contact"
            tags:
            - "Contacts"
            securedBy:
            - scheme: "#/contract/securitySchemes/56f788ca-2ee8-4b6f-9e51-da9f22102bac"
              scopes: []
            bodies:
            - type: "#/contract/types/a7f2f161-5a8e-4a02-8199-6833ad1dbdd6"
              examples:
              - value: |-
                  {
                    "firstName": "John",
                    "lastName": "Smith",
                    "birthday": 152755200000,
                    "active": true,
                    "rank": 1,
                    "company": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f"
                  }
            responses:
              "34b42504-19d4-42a7-8c94-04ca019e414c":
                status: "200"
                description: "Status 200"
                bodies:
                - type: "#/contract/types/a7f2f161-5a8e-4a02-8199-6833ad1dbdd6"
                  examples:
                  - value: |-
                      {
                        "id": "0e8dd830-ad98-11e6-bf2e-47644ada7c0f",
                        "firstName": "John",
                        "lastName": "Smith",
                        "birthday": 152755200000,
                        "active": true,
                        "rank": 1,
                        "company": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f"
                      }
          "03d20911-818b-48ab-b344-38cc30baf932":
            name: "Delete a Contact"
            method: "DELETE"
            description: "Deletes a Contact"
            tags:
            - "Contacts"
            securedBy:
            - scheme: "#/contract/securitySchemes/56f788ca-2ee8-4b6f-9e51-da9f22102bac"
              scopes: []
            responses:
              "4d8a64e6-f132-4062-981e-4c1e4e84dfb3":
                status: "200"
                description: "Status 200"
    types:
      "29cfc35d-5765-4775-8b4c-d9f9968d6307":
        name: "Company"
        type: "OBJECT"
        description: "The datatype of a Company"
        section: "#/contract/sections/f99f937f-a232-4513-b133-3ad59b59da38"
        properties:
        - name: "id"
          type: "STRING"
          description: "Auto-generated primary key field"
          required: true
        - name: "name"
          type: "STRING"
          required: true
        - name: "tags"
          type: "ARRAY"
          items:
            type: "STRING"
            pattern: "[a-zA-Z]+"
          examples:
          - value: "[\"brewery\", \"beer\", \"ale\"]"
        - name: "address"
          type: "OBJECT"
          required: true
          properties:
          - name: "street"
            type: "STRING"
            required: true
          - name: "city"
            type: "STRING"
            required: true
          - name: "zipcode"
            type: "STRING"
            required: true
            pattern: "[0-9]*"
        examples:
        - value: |-
            {
              "id": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f",
              "name": "George Street Brewery",
              "address":{
                "street": "2 place de la Defense",
                "zipcode": "92053",
                "city": "Paris"
              },
              "tags":[
                "brewery",
                "beer",
                "ale"
              ]
            }
      a7f2f161-5a8e-4a02-8199-6833ad1dbdd6:
        name: "Contact"
        type: "OBJECT"
        description: "The datatype of a Contact"
        section: "#/contract/sections/7ea96dc3-52a9-4133-bccc-859625c568a9"
        properties:
        - name: "id"
          type: "STRING"
          description: "Auto-generated primary key field"
          required: true
          examples:
          - value: "0e8ffb10-ad98-11e6-bf2e-47644ada7c0f"
        - name: "firstName"
          type: "STRING"
          required: true
          examples:
          - value: "Kurt"
        - name: "lastName"
          type: "STRING"
          required: true
          examples:
          - value: "Williams"
        - name: "birthday"
          type: "INTEGER"
          format: "INT64"
          description: "Birthday as unix timestamp (in ms)"
          examples:
          - value: 173664000000
          - value: 383270400000
        - name: "active"
          type: "BOOLEAN"
          default: true
        - name: "rank"
          type: "INTEGER"
          format: "INT32"
          minimum: 1
          examples:
          - value: 1
          - value: 2
          - value: 3
        - name: "company"
          type: "STRING"
          description: "This property is a reference to a Company"
          examples:
          - value: "0e8c9fb0-ad98-11e6-bf2e-47644ada7c0f"
        examples:
        - value: |-
            {
              "id": "0e8dd830-ad98-11e6-bf2e-47644ada7c0f",
              "firstName": "John",
              "lastName": "Smith",
              "birthday": 152755200000,
              "active": true,
              "rank": 1,
              "company": "0e8cedd0-ad98-11e6-bf2e-47644ada7c0f"
            }
      "88fc9d36-2692-44a1-8c9b-5429bc8fab98":
        name: "Error"
        type: "OBJECT"
        description: "This general error structure is used throughout this API."
        section: "#/contract/sections/5b73262d-2dc4-4388-9755-d8631e389bd7"
        properties:
        - name: "code"
          type: "INTEGER"
          required: true
          minimum: 400
          maximum: 599
        - name: "description"
          type: "STRING"
          examples:
          - value: "Bad query parameter [$size]: Invalid integer value [abc]"
          - value: "The server understood the request, but is refusing to fulfill it"
        - name: "reasonPhrase"
          type: "STRING"
          examples:
          - value: "Bad Request"
          - value: "Forbidden"
        examples:
        - value: |-
            {
              "code": 400,
              "description": "Bad query parameter [$size]: Invalid integer value [abc]",
              "reasonPhrase": "Bad Request"
            }
    texts:
      "76415f4b-8a2c-4842-8321-92724900907c":
        title: "Authentication"
        content: |-
          This API is secured using Basic Authentication.

          All **read operations are open** and don't require authentication. However, all **write operations require authentication**.
        section: "#/contract/sections/5b73262d-2dc4-4388-9755-d8631e389bd7"
      e761f684-32c9-4881-945f-ab24db5f0e1f:
        title: "Error handling"
        content: |+
          This API uses standard HTTP status codes to indicate the status of a response.

          There are two main categories of error responses. Each have a different response payload structure.

          * Simple errors
          * Detailed errors


          # Simple errors

          | Name | Code | Description |
          | -------- | -------- | -------- |
          | Bad request     | 400     | The request was unacceptable.     |
          | Unauthorized     | 401     | The request has not been applied because it lacks valid authentication credentials for the target resource.     |
          | Forbidden     | 403     | The server understood the request, but is refusing to fulfill it.     |
          | Not Found     | 404     | The server has not found anything matching the request URI.     |
          | Not acceptable     | 406     | The server cannot return a response in the format that was requested by the client.     |
          | Unsupported Media Type     | 415     | The server refuses to process the request because the entity of the request is in a format not supported by the requested resource for the requested method.     |
          Too many requests     | 429     | Too many requests hit the API too quickly     |
          | Server error     | 500     | A technical error occurred.  |






          # Detailed errors
          | Name | Code | Description |
          | -------- | -------- | -------- |
          | Unprocessable entity     | 422     | The server understands the content type of the request entity, which has a correct syntax, but failed to process the contained instructions.     |




        section: "#/contract/sections/5b73262d-2dc4-4388-9755-d8631e389bd7"
  components:
    pathVariables:
      "238bfd13-9110-4da8-8d30-5eac4e67b88f":
        name: "contactid"
        componentName: "contactid"
        type: "STRING"
        description: "Identifier of the Contact"
        required: true
        examples:
        - value: "0e8dd830-ad98-11e6-bf2e-47644ada7c0f"
      "6dc2cfe5-a655-4b92-b0eb-0c3bfcc2e8c2":
        name: "companyid"
        componentName: "companyid"
        type: "STRING"
        description: "Identifier of the Company"
        required: true
        examples:
        - value: "0e8c9fb0-ad98-11e6-bf2e-47644ada7c0f"
    queryParameters:
      "7160507d-7112-4717-88e3-e64c16a47654":
        name: "$size"
        componentName: "$size"
        type: "INTEGER"
        description: "Size of the page to retrieve."
        examples:
        - value: 10
      b931de52-3eeb-47c0-81a9-693f6c6a504c:
        name: "$page"
        componentName: "$page"
        type: "INTEGER"
        description: "Number of the page to retrieve."
        examples:
        - value: 1
        - value: 42
      "5b4bd8e1-5e73-4e7f-a671-7c31ea287d33":
        name: "$sort"
        componentName: "$sort"
        type: "STRING"
        description: "Order in which to retrieve the results. Multiple sort criteria can be passed."
        examples:
        - value: "birthday DESC"
        - value: "birthday ASC,rank DESC"
    headers:
      "586c6ef9-1ed7-4770-9f51-1e522061d2a8":
        name: "X-Page-Count"
        componentName: "X-Page-Count"
        type: "INTEGER"
        examples:
        - value: 1
      "50aa2973-07c5-45be-960e-b53f8751b1e9":
        name: "X-Page-Number"
        componentName: "X-Page-Number"
        type: "INTEGER"
        examples:
        - value: 1
      "8f2a1ed8-7a2f-4c89-ba15-b05c7bc29ae2":
        name: "X-Page-Size"
        componentName: "X-Page-Size"
        type: "INTEGER"
        examples:
        - value: 25
      "7b587c76-48da-49bb-a9d7-924e450932f9":
        name: "X-Total-Count"
        componentName: "X-Total-Count"
        type: "INTEGER"
        examples:
        - value: 2
    responses:
      a0f2f195-3599-4227-a9a0-495422576efe:
        status: "400"
        componentName: "Status 400"
        bodies:
        - type: "#/contract/types/88fc9d36-2692-44a1-8c9b-5429bc8fab98"
          mediaTypes:
          - "application/json"
api-tryin: |-
  {
    "version" : 6,
    "entities" : [ {
      "entity" : {
        "type" : "Project",
        "name" : "Contacts API 4.1.0",
        "description" : "An API for keeping track of your contacts and the companies they work for.",
        "importedFrom" : "137bdf8f-0df9-4a55-8117-a3e7966b7973"
      },
      "children" : [ {
        "entity" : {
          "type" : "Service",
          "name" : "General"
        }
      }, {
        "entity" : {
          "type" : "Service",
          "name" : "Contacts",
          "description" : ""
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "a72bbf0f-43b7-4c30-a35f-b4ceb2fdf349",
            "name" : "Get the list of Contacts",
            "description" : "Loads a list of Contact",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/contacts/",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "$size",
                  "value" : "10",
                  "enabled" : false
                }, {
                  "name" : "$page",
                  "value" : "1",
                  "enabled" : false
                }, {
                  "name" : "$sort",
                  "value" : "birthday DESC",
                  "enabled" : false
                }, {
                  "name" : "firstName",
                  "value" : "John",
                  "enabled" : false
                }, {
                  "name" : "lastName",
                  "value" : "Doe",
                  "enabled" : false
                }, {
                  "name" : "active",
                  "value" : "true",
                  "enabled" : false
                }, {
                  "name" : "company",
                  "value" : "0e8c9fb0-ad98-11e6-bf2e-47644ada7c0f",
                  "enabled" : false
                } ]
              }
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "9a642024-7464-4956-a3d2-8294ef3cb0a1",
            "name" : "Create a Contact",
            "description" : "Adds a Contact",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/contacts/"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : "{\n  \"firstName\": \"John\",\n  \"lastName\": \"Smith\",\n  \"birthday\": 152755200000,\n  \"active\": true,\n  \"rank\": 1,\n  \"company\": \"0e8cedd0-ad98-11e6-bf2e-47644ada7c0f\"\n}"
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "c29715de-044b-4978-90d8-120ff4f2dee9",
            "name" : "Load a Contact",
            "description" : "Loads a Contact",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/contacts/{contactid}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "91b8076b-f416-4ebf-bc09-1cf615a3cbe2",
            "name" : "Update a Contact",
            "description" : "Updates a Contact",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/contacts/{contactid}"
            },
            "method" : {
              "link" : "",
              "name" : "PUT",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : "{\n  \"firstName\": \"John\",\n  \"lastName\": \"Smith\",\n  \"birthday\": 152755200000,\n  \"active\": true,\n  \"rank\": 1,\n  \"company\": \"0e8cedd0-ad98-11e6-bf2e-47644ada7c0f\"\n}"
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "03d20911-818b-48ab-b344-38cc30baf932",
            "name" : "Delete a Contact",
            "description" : "Deletes a Contact",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/contacts/{contactid}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        } ]
      }, {
        "entity" : {
          "type" : "Service",
          "name" : "Companies"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "53f1cb6b-94c8-4dc9-af1b-4289ed1365a4",
            "name" : "Load the list of Companies",
            "description" : "Loads a list of Company",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/companies/",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "$size",
                  "value" : "10",
                  "enabled" : false
                }, {
                  "name" : "$page",
                  "value" : "1",
                  "enabled" : false
                }, {
                  "name" : "$sort",
                  "value" : "birthday DESC",
                  "enabled" : false
                }, {
                  "name" : "name",
                  "value" : "George Street Brewery",
                  "enabled" : false
                } ]
              }
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "911f688c-17e9-4d5b-b5f8-d925be90db2a",
            "name" : "Create a new Company",
            "description" : "Adds a Company",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/companies/"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : "{\n  \"name\": \"George Street Brewery\",\n  \"address\":{\n    \"street\": \"2 place de la Defense\",\n    \"zipcode\": \"92053\",\n    \"city\": \"Paris\"\n  },\n  \"tags\":[\n    \"brewery\",\n    \"beer\",\n    \"ale\"\n  ]\n}"
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "28030be1-158e-496c-bd7d-796a45a04c19",
            "name" : "Load a Company",
            "description" : "Loads a Company",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/companies/{companyid}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "03e04a76-ac15-44ca-b7cf-0d3c8bb90936",
            "name" : "Update a Company",
            "description" : "Updates a Company",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/companies/{companyid}"
            },
            "method" : {
              "link" : "",
              "name" : "PUT",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : "{\n  \"name\": \"George Street Brewery\",\n  \"address\":{\n    \"street\": \"2 place de la Defense\",\n    \"zipcode\": \"92053\",\n    \"city\": \"Paris\"\n  },\n  \"tags\":[\n    \"brewery\",\n    \"beer\",\n    \"ale\"\n  ]\n}"
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "e8cce56b-3868-475d-b18d-5d2688603820",
            "name" : "Delete a Company",
            "description" : "Deletes a Company",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/companies/{companyid}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        } ]
      } ]
    } ],
    "environments" : [ {
      "name" : "Contacts API 4.1.0",
      "importedFrom" : {
        "projectId" : "137bdf8f-0df9-4a55-8117-a3e7966b7973"
      },
      "variables" : {
        "0200d751-e5c5-408e-99d1-01145d1960cd" : {
          "name" : "BaseUrl",
          "value" : "https://example.com",
          "enabled" : true,
          "private" : false
        }
      }
    } ]
  }
---
