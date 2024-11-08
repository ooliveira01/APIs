---
# NOTICE: Copyright 2024 Talend SA, Talend, Inc., and affiliates. All Rights Reserved. Customer’s use of the software contained herein is subject to the terms and conditions of the Agreement between Customer and Talend.
layout: "apiDefinition_1.1.0"
api-definition:
  specVersion: "4.1.0"
  info:
    name: "Petstore API"
    version: "4.1.0"
    description: "This is a sample server Petstore server.  You can find out more about Swagger at [http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).  For this sample, you can use the api key `special-key` to test the authorization filters."
    license:
      name: "Apache 2.0"
      url: "http://www.apache.org/licenses/LICENSE-2.0.html"
    contact:
      email: "apiteam@swagger.io"
    termsOfService: "http://swagger.io/terms/"
  contract:
    baseUrls:
    - url: "http://petstore.swagger.io/v2"
      isPublished: true
    mediaTypes:
    - "application/json"
    sections:
    - name: "Pet"
      elementOrder:
      - "#/contract/resources/d317e55c-d040-4bf8-8ef7-ba4a085715aa"
      - "#/contract/resources/b150c5cd-9dac-426d-a805-c872f4479d51"
      - "#/contract/resources/939601a0-2048-40b9-8581-8d040c397635"
      - "#/contract/resources/24a6a5f3-0574-4cdb-a7ef-f7ba56a6a77e"
      - "#/contract/resources/2affd790-b227-4d3e-a2ca-e4f09bdfeac1"
      - "#/contract/types/70ae3ecc-a301-4a6c-92b6-3bf8e187db70"
      - "#/contract/types/76169a87-9889-4514-a562-64d2a183edd5"
      - "#/contract/types/4de54ed3-b0ed-41a8-9274-4ca811b15e50"
      - "#/contract/types/49345d84-18de-472a-bb9d-453af041b705"
    - name: "Store"
      elementOrder:
      - "#/contract/resources/08b10a12-2dee-44a9-ab28-b8d530fc8c0f"
      - "#/contract/resources/9d63ca42-84b5-4db8-8394-89086b642a23"
      - "#/contract/resources/0f3d8e33-c629-4bc1-bd99-6dc52fe01de9"
      - "#/contract/types/134e8b5a-baaa-4139-a737-215b920fe01c"
    - name: "User"
      elementOrder:
      - "#/contract/resources/5bd20850-4c4f-433a-ac60-17bac2b754f8"
      - "#/contract/resources/4b68ce26-6313-4b47-ae24-9f3c7127fd05"
      - "#/contract/resources/5df9d483-50b5-41ba-b6c3-944238daba34"
      - "#/contract/resources/2c82ce5e-aec4-4dea-853a-a3bfdaba3bc0"
      - "#/contract/resources/471f7342-55a3-4aca-b1f4-681baefa7efc"
      - "#/contract/resources/0f0668e0-6d46-4ae7-806b-aab28c6a98ac"
      - "#/contract/types/2149b9ba-6641-47e2-9a93-4da53963924d"
    securitySchemes:
      b099ae19-2ecb-451e-8020-72ee79d0012a:
        name: "petstore_auth"
        type: "oauth2"
        settings:
          authorizationUri: "http://petstore.swagger.io/oauth/dialog"
          authorizationGrants:
          - "implicit"
          scopes:
            "7f04b9ab-a99c-455c-8d8a-f71b512fd0fb":
              name: "write:pets"
              description: "modify pets in your account"
            "9a4dccb7-ab47-43c4-9d38-9e9ddc3b607e":
              name: "read:pets"
              description: "read your pets"
      "0f28d2b1-9b1b-4396-a721-b0e216d951ec":
        name: "api_key"
        type: "custom"
        describedBy:
          headers:
          - name: "api_key"
            type: "STRING"
    resources:
      "939601a0-2048-40b9-8581-8d040c397635":
        path: "/pet"
        section: "#/contract/sections/20bb30fb-f535-419d-99ba-da12729ed723"
        operations:
          "3f9676e7-9c6f-49be-ad84-166d46d41957":
            name: "Update an existing pet"
            method: "PUT"
            description: ""
            operationId: "updatePet"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a"
              scopes:
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/7f04b9ab-a99c-455c-8d8a-f71b512fd0fb"
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/9a4dccb7-ab47-43c4-9d38-9e9ddc3b607e"
            bodies:
            - type: "#/contract/types/70ae3ecc-a301-4a6c-92b6-3bf8e187db70"
              mediaTypes:
              - "application/json"
              - "application/xml"
            responses:
              "439855e5-cb2d-47c3-ae2f-32592cd07929":
                status: "400"
                description: "Invalid ID supplied"
              b601a2cf-8d2b-4e79-bb94-0bf95f83e988:
                status: "404"
                description: "Pet not found"
              "1157e6bf-5e13-444a-a782-e1824628529e":
                status: "405"
                description: "Validation exception"
          c1e5802a-03f0-4e25-91d2-c7e5e8f66ed0:
            name: "Add a new pet to the store"
            method: "POST"
            description: ""
            operationId: "addPet"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a"
              scopes:
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/7f04b9ab-a99c-455c-8d8a-f71b512fd0fb"
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/9a4dccb7-ab47-43c4-9d38-9e9ddc3b607e"
            bodies:
            - type: "#/contract/types/70ae3ecc-a301-4a6c-92b6-3bf8e187db70"
              mediaTypes:
              - "application/json"
              - "application/xml"
            responses:
              f76cb436-2bb6-4a2a-9375-18ae015a4a32:
                status: "405"
                description: "Invalid input"
      b150c5cd-9dac-426d-a805-c872f4479d51:
        path: "/pet/findByStatus"
        section: "#/contract/sections/20bb30fb-f535-419d-99ba-da12729ed723"
        operations:
          "5613e3dd-3da4-4e1d-b769-d754cd6e8665":
            name: "Finds Pets by status"
            method: "GET"
            description: "Multiple status values can be provided with comma separated strings"
            operationId: "findPetsByStatus"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a"
              scopes:
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/7f04b9ab-a99c-455c-8d8a-f71b512fd0fb"
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/9a4dccb7-ab47-43c4-9d38-9e9ddc3b607e"
            queryParameters:
            - name: "status"
              type: "ARRAY"
              description: "Status values that need to be considered for filter"
              required: true
              items:
                type: "STRING"
                default: "available"
                enum:
                - "available"
                - "pending"
                - "sold"
            responses:
              "777be283-c006-47e4-af26-182e0675a55f":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "ARRAY"
                  items:
                    type: "#/contract/types/70ae3ecc-a301-4a6c-92b6-3bf8e187db70"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "8b6c4995-2ce8-4893-b6ef-8ef7069cf1b9":
                status: "400"
                description: "Invalid status value"
      d317e55c-d040-4bf8-8ef7-ba4a085715aa:
        path: "/pet/findByTags"
        section: "#/contract/sections/20bb30fb-f535-419d-99ba-da12729ed723"
        operations:
          "7281eebe-9c61-49e9-8a42-fbb62f260a7b":
            name: "Finds Pets by tags"
            method: "GET"
            description: "Muliple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing."
            operationId: "findPetsByTags"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a"
              scopes:
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/7f04b9ab-a99c-455c-8d8a-f71b512fd0fb"
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/9a4dccb7-ab47-43c4-9d38-9e9ddc3b607e"
            queryParameters:
            - name: "tags"
              type: "ARRAY"
              description: "Tags to filter by"
              required: true
              items:
                type: "STRING"
            responses:
              "2e9e0bcb-a8cd-451d-b3e1-16c6ac809eb3":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "ARRAY"
                  items:
                    type: "#/contract/types/70ae3ecc-a301-4a6c-92b6-3bf8e187db70"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              e10038a6-1988-4b80-9a22-9f51bb905cad:
                status: "400"
                description: "Invalid tag value"
      "24a6a5f3-0574-4cdb-a7ef-f7ba56a6a77e":
        path: "/pet/{petId}"
        section: "#/contract/sections/20bb30fb-f535-419d-99ba-da12729ed723"
        pathVariables:
        - name: "petId"
          type: "INTEGER"
          description: "ID of pet to return"
          required: true
        operations:
          "14833cf2-fe2b-41fc-b687-4dc691396d0c":
            name: "Find pet by ID"
            method: "GET"
            description: "Returns a single pet"
            operationId: "getPetById"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/0f28d2b1-9b1b-4396-a721-b0e216d951ec"
              scopes: []
            responses:
              a703e38c-5bae-41f9-8926-2bb0546c5045:
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/70ae3ecc-a301-4a6c-92b6-3bf8e187db70"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              be6907c7-1102-4088-aa78-a23183e39803:
                status: "400"
                description: "Invalid ID supplied"
              e87f60da-1354-4b8d-91cc-6cac448880d8:
                status: "404"
                description: "Pet not found"
          "89a3b68e-2f1c-4477-bfb6-94fe62a9968b":
            name: "Updates a pet in the store with form data"
            method: "POST"
            description: ""
            operationId: "updatePetWithForm"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a"
              scopes:
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/7f04b9ab-a99c-455c-8d8a-f71b512fd0fb"
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/9a4dccb7-ab47-43c4-9d38-9e9ddc3b607e"
            bodies:
            - type: "OBJECT"
              properties:
              - name: "name"
                type: "STRING"
                description: "Updated name of the pet"
              - name: "status"
                type: "STRING"
                description: "Updated status of the pet"
              mediaTypes:
              - "application/x-www-form-urlencoded"
            responses:
              "6eae7b02-3cda-436a-a3e0-b5a6a332c70e":
                status: "405"
                description: "Invalid input"
          bb1fe2d4-f35d-4b4b-a4f7-07f9388ab6b0:
            name: "Deletes a pet"
            method: "DELETE"
            description: ""
            operationId: "deletePet"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a"
              scopes:
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/7f04b9ab-a99c-455c-8d8a-f71b512fd0fb"
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/9a4dccb7-ab47-43c4-9d38-9e9ddc3b607e"
            headers:
            - name: "api_key"
              type: "STRING"
            responses:
              e834f11a-513d-4a5c-9158-7f080f735670:
                status: "400"
                description: "Invalid ID supplied"
              "56220466-af6d-43b7-b572-56a18eac36ce":
                status: "404"
                description: "Pet not found"
      "2affd790-b227-4d3e-a2ca-e4f09bdfeac1":
        path: "/pet/{petId}/uploadImage"
        section: "#/contract/sections/20bb30fb-f535-419d-99ba-da12729ed723"
        pathVariables:
        - name: "petId"
          type: "INTEGER"
          format: "INT64"
          description: "ID of pet to return"
          required: true
        operations:
          "3fb37135-bd6c-444a-a622-35ca63a635cc":
            name: "uploads an image"
            method: "POST"
            description: ""
            operationId: "uploadFile"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a"
              scopes:
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/7f04b9ab-a99c-455c-8d8a-f71b512fd0fb"
              - "#/contract/securitySchemes/b099ae19-2ecb-451e-8020-72ee79d0012a/settings/scopes/9a4dccb7-ab47-43c4-9d38-9e9ddc3b607e"
            bodies:
            - type: "OBJECT"
              properties:
              - name: "additionalMetadata"
                type: "STRING"
                description: "Additional data to pass to server"
              - name: "file"
                type: "FILE"
                description: "file to upload"
              mediaTypes:
              - "multipart/form-data"
            responses:
              "22da3425-bb0d-4ef5-9c3f-a92e5767e168":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/49345d84-18de-472a-bb9d-453af041b705"
                  mediaTypes:
                  - "application/json"
      "0f3d8e33-c629-4bc1-bd99-6dc52fe01de9":
        path: "/store/inventory"
        section: "#/contract/sections/9a2fbf39-fb02-47a2-bff3-859a6d33f659"
        operations:
          b70fade5-835b-44b5-ad34-a2e2bcd0ddb2:
            name: "Returns pet inventories by status"
            method: "GET"
            description: "Returns a map of status codes to quantities"
            operationId: "getInventory"
            tags:
            - "store"
            securedBy:
            - scheme: "#/contract/securitySchemes/0f28d2b1-9b1b-4396-a721-b0e216d951ec"
              scopes: []
            responses:
              "2fcc4567-c539-4df3-8a3c-c2eac6da440e":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "OBJECT"
                  mediaTypes:
                  - "application/json"
      "08b10a12-2dee-44a9-ab28-b8d530fc8c0f":
        path: "/store/order"
        section: "#/contract/sections/9a2fbf39-fb02-47a2-bff3-859a6d33f659"
        operations:
          "46e111cb-8d7e-4265-8342-4d38df8f3b99":
            name: "Place an order for a pet"
            method: "POST"
            description: ""
            operationId: "placeOrder"
            tags:
            - "store"
            bodies:
            - type: "#/contract/types/134e8b5a-baaa-4139-a737-215b920fe01c"
            responses:
              "7deb99d8-eed0-4fdf-b2ba-28b1dbf5da05":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/134e8b5a-baaa-4139-a737-215b920fe01c"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "29ad27a5-44ae-4f1c-9063-b81b4c2e15f3":
                status: "400"
                description: "Invalid Order"
      "9d63ca42-84b5-4db8-8394-89086b642a23":
        path: "/store/order/{orderId}"
        section: "#/contract/sections/9a2fbf39-fb02-47a2-bff3-859a6d33f659"
        pathVariables:
        - name: "orderId"
          type: "INTEGER"
          format: "INT64"
          required: true
          minimum: 1
          maximum: 10
        operations:
          "8797b365-50cb-4685-a5aa-08b59457dfaa":
            name: "Find purchase order by ID"
            method: "GET"
            description: "For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions"
            operationId: "getOrderById"
            tags:
            - "store"
            responses:
              "04fa78ff-fa6a-4a7a-8762-3d98d2765c7a":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/134e8b5a-baaa-4139-a737-215b920fe01c"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "8cc00f05-5a9f-4778-b9c1-a0044c244fa7":
                status: "400"
                description: "Invalid ID supplied"
              "4dcd11fa-f0ce-457e-b588-9c23a07426b7":
                status: "404"
                description: "Order not found"
          "8ff2781d-396f-4714-a6b8-67ec7a00eebd":
            name: "Delete purchase order by ID"
            method: "DELETE"
            description: "For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors"
            operationId: "deleteOrder"
            tags:
            - "store"
            responses:
              "2a9e51fe-6c4d-4ed4-a2ee-b90a695af4ab":
                status: "400"
                description: "Invalid ID supplied"
              "001fb8eb-c65c-436d-883d-ff92edcdf07d":
                status: "404"
                description: "Order not found"
      "5bd20850-4c4f-433a-ac60-17bac2b754f8":
        path: "/user"
        section: "#/contract/sections/f64cabd0-f2db-4377-a9cb-8c40c3983430"
        operations:
          "98b9689c-2281-44fc-b4b9-adbcdcc5a27b":
            name: "Create user"
            method: "POST"
            description: "This can only be done by the logged in user."
            operationId: "createUser"
            tags:
            - "user"
            bodies:
            - type: "#/contract/types/2149b9ba-6641-47e2-9a93-4da53963924d"
      "4b68ce26-6313-4b47-ae24-9f3c7127fd05":
        path: "/user/createWithArray"
        section: "#/contract/sections/f64cabd0-f2db-4377-a9cb-8c40c3983430"
        operations:
          "2e52d38d-daf0-49f0-90df-2d098b7547b5":
            name: "Creates list of users with given input array"
            method: "POST"
            description: ""
            operationId: "createUsersWithArrayInput"
            tags:
            - "user"
            bodies:
            - type: "ARRAY"
              items:
                type: "#/contract/types/2149b9ba-6641-47e2-9a93-4da53963924d"
      "5df9d483-50b5-41ba-b6c3-944238daba34":
        path: "/user/createWithList"
        section: "#/contract/sections/f64cabd0-f2db-4377-a9cb-8c40c3983430"
        operations:
          bbba5715-de17-4bbd-af17-2a19e36b892a:
            name: "Creates list of users with given input array"
            method: "POST"
            description: ""
            operationId: "createUsersWithListInput"
            tags:
            - "user"
            bodies:
            - type: "ARRAY"
              items:
                type: "#/contract/types/2149b9ba-6641-47e2-9a93-4da53963924d"
      "471f7342-55a3-4aca-b1f4-681baefa7efc":
        path: "/user/login"
        section: "#/contract/sections/f64cabd0-f2db-4377-a9cb-8c40c3983430"
        operations:
          "1debb95c-d86c-4c42-972f-de4bbc15b8a1":
            name: "Logs user into the system"
            method: "GET"
            description: ""
            operationId: "loginUser"
            tags:
            - "user"
            queryParameters:
            - name: "username"
              type: "STRING"
              description: "The user name for login"
              required: true
            - name: "password"
              type: "STRING"
              description: "The password for login in clear text"
              required: true
            responses:
              c3b551d1-b42d-41bf-a11e-7a61c3d2f838:
                status: "200"
                description: "successful operation"
                headers:
                - name: "X-Rate-Limit"
                  type: "INTEGER"
                  format: "INT32"
                  description: "calls per hour allowed by the user"
                - name: "X-Expires-After"
                  type: "DATETIME"
                  description: "date in UTC when token expires"
                bodies:
                - type: "STRING"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "5b5ba049-4abd-40a0-ae09-e475d4614a3b":
                status: "400"
                description: "Invalid username/password supplied"
      "0f0668e0-6d46-4ae7-806b-aab28c6a98ac":
        path: "/user/logout"
        section: "#/contract/sections/f64cabd0-f2db-4377-a9cb-8c40c3983430"
        operations:
          e2289a34-a738-4ea1-83fa-53545e4cf948:
            name: "Logs out current logged in user session"
            method: "GET"
            operationId: "logoutUser"
            tags:
            - "user"
            responses:
              "7f69854d-05d3-447f-90ce-984ae6c5723b":
                status: "200"
      "2c82ce5e-aec4-4dea-853a-a3bfdaba3bc0":
        path: "/user/{username}"
        section: "#/contract/sections/f64cabd0-f2db-4377-a9cb-8c40c3983430"
        pathVariables:
        - name: "username"
          type: "STRING"
          description: "The name that needs to be fetched. Use user1 for testing."
          required: true
        operations:
          de06cd51-f22b-43d3-8a2d-6338492d5a98:
            name: "Get user by user name"
            method: "GET"
            description: ""
            operationId: "getUserByName"
            tags:
            - "user"
            responses:
              "3c95b463-ccaa-4fea-ab90-d980cabd9d22":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/2149b9ba-6641-47e2-9a93-4da53963924d"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "9fd5dd5f-64ba-4bef-a0a2-7613a78a8809":
                status: "400"
                description: "Invalid username supplied"
              "77f966a7-a738-463b-b378-29244bd6a7c2":
                status: "404"
                description: "User not found"
          eef912c3-30fc-439d-8289-3d4872f222bf:
            name: "Updated user"
            method: "PUT"
            description: "This can only be done by the logged in user."
            operationId: "updateUser"
            tags:
            - "user"
            bodies:
            - type: "#/contract/types/2149b9ba-6641-47e2-9a93-4da53963924d"
            responses:
              c4126c81-fc09-4d29-ae00-7c869dc96519:
                status: "400"
                description: "Invalid user supplied"
              ca4fb369-f41c-4dfe-bf0a-8940a69de77c:
                status: "404"
                description: "User not found"
          adffa1c6-4925-4ded-ac17-4cd82a561846:
            name: "Delete user"
            method: "DELETE"
            description: "This can only be done by the logged in user."
            operationId: "deleteUser"
            tags:
            - "user"
            responses:
              "81421c56-b19a-4a71-835e-01b1780ee8de":
                status: "400"
                description: "Invalid username supplied"
              "8cf71886-c22b-4852-8864-70d458891556":
                status: "404"
                description: "User not found"
    types:
      "134e8b5a-baaa-4139-a737-215b920fe01c":
        name: "Order"
        type: "OBJECT"
        section: "#/contract/sections/9a2fbf39-fb02-47a2-bff3-859a6d33f659"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "petId"
          type: "INTEGER"
          format: "INT64"
        - name: "quantity"
          type: "INTEGER"
          format: "INT32"
        - name: "shipDate"
          type: "DATETIME"
        - name: "status"
          type: "STRING"
          description: "Order Status"
          enum:
          - "placed"
          - "approved"
          - "delivered"
        - name: "complete"
          type: "BOOLEAN"
          default: false
      "4de54ed3-b0ed-41a8-9274-4ca811b15e50":
        name: "Category"
        type: "OBJECT"
        section: "#/contract/sections/20bb30fb-f535-419d-99ba-da12729ed723"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "name"
          type: "STRING"
      "2149b9ba-6641-47e2-9a93-4da53963924d":
        name: "User"
        type: "OBJECT"
        section: "#/contract/sections/f64cabd0-f2db-4377-a9cb-8c40c3983430"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "username"
          type: "STRING"
        - name: "firstName"
          type: "STRING"
        - name: "lastName"
          type: "STRING"
        - name: "email"
          type: "STRING"
        - name: "password"
          type: "STRING"
        - name: "phone"
          type: "STRING"
        - name: "userStatus"
          type: "INTEGER"
          format: "INT32"
          description: "User Status"
      "76169a87-9889-4514-a562-64d2a183edd5":
        name: "Tag"
        type: "OBJECT"
        section: "#/contract/sections/20bb30fb-f535-419d-99ba-da12729ed723"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "name"
          type: "STRING"
      "70ae3ecc-a301-4a6c-92b6-3bf8e187db70":
        name: "Pet"
        type: "OBJECT"
        section: "#/contract/sections/20bb30fb-f535-419d-99ba-da12729ed723"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "category"
          type: "#/contract/types/4de54ed3-b0ed-41a8-9274-4ca811b15e50"
        - name: "name"
          type: "STRING"
          required: true
          examples:
          - value: "doggie"
        - name: "photoUrls"
          type: "ARRAY"
          required: true
          items:
            type: "STRING"
        - name: "tags"
          type: "ARRAY"
          items:
            type: "#/contract/types/76169a87-9889-4514-a562-64d2a183edd5"
        - name: "status"
          type: "STRING"
          description: "pet status in the store"
          enum:
          - "available"
          - "pending"
          - "sold"
      "49345d84-18de-472a-bb9d-453af041b705":
        name: "ApiResponse"
        type: "OBJECT"
        section: "#/contract/sections/20bb30fb-f535-419d-99ba-da12729ed723"
        properties:
        - name: "code"
          type: "INTEGER"
          format: "INT32"
        - name: "type"
          type: "STRING"
        - name: "message"
          type: "STRING"
  components: {}
api-tryin: |-
  {
    "version" : 6,
    "entities" : [ {
      "entity" : {
        "type" : "Project",
        "name" : "Petstore API 4.1.0",
        "description" : "This is a sample server Petstore server.  You can find out more about Swagger at [http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).  For this sample, you can use the api key `special-key` to test the authorization filters.",
        "importedFrom" : "4f8884b3-15cb-44a4-a518-16fe3e9956a3"
      },
      "children" : [ {
        "entity" : {
          "type" : "Service",
          "name" : "Pet"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "7281eebe-9c61-49e9-8a42-fbb62f260a7b",
            "name" : "Finds Pets by tags",
            "description" : "Muliple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/findByTags",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "tags",
                  "value" : "",
                  "enabled" : true
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
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "5613e3dd-3da4-4e1d-b769-d754cd6e8665",
            "name" : "Finds Pets by status",
            "description" : "Multiple status values can be provided with comma separated strings",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/findByStatus",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "status",
                  "value" : "",
                  "enabled" : true
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
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "3f9676e7-9c6f-49be-ad84-166d46d41957",
            "name" : "Update an existing pet",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet"
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
              "enabled" : false,
              "name" : "Content-Type",
              "value" : "application/xml"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "c1e5802a-03f0-4e25-91d2-c7e5e8f66ed0",
            "name" : "Add a new pet to the store",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet"
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
              "enabled" : false,
              "name" : "Content-Type",
              "value" : "application/xml"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "14833cf2-fe2b-41fc-b687-4dc691396d0c",
            "name" : "Find pet by ID",
            "description" : "Returns a single pet",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : false,
              "name" : "api_key",
              "value" : "${\"Api_keyHeaderApi_key\"}"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "89a3b68e-2f1c-4477-bfb6-94fe62a9968b",
            "name" : "Updates a pet in the store with form data",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/x-www-form-urlencoded"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Form",
              "formBody" : {
                "items" : [ {
                  "enabled" : false,
                  "name" : "name",
                  "value" : "",
                  "type" : "Text"
                }, {
                  "enabled" : false,
                  "name" : "status",
                  "value" : "",
                  "type" : "Text"
                } ],
                "encoding" : "application/x-www-form-urlencoded"
              }
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "bb1fe2d4-f35d-4b4b-a4f7-07f9388ab6b0",
            "name" : "Deletes a pet",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ {
              "enabled" : false,
              "name" : "api_key",
              "value" : ""
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "3fb37135-bd6c-444a-a622-35ca63a635cc",
            "name" : "uploads an image",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}/uploadImage"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "multipart/form-data"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Form",
              "formBody" : {
                "items" : [ {
                  "enabled" : false,
                  "name" : "additionalMetadata",
                  "value" : "",
                  "type" : "Text"
                }, {
                  "enabled" : false,
                  "name" : "file",
                  "type" : "File"
                } ],
                "encoding" : "multipart/form-data"
              }
            }
          }
        } ]
      }, {
        "entity" : {
          "type" : "Service",
          "name" : "Store"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "46e111cb-8d7e-4265-8342-4d38df8f3b99",
            "name" : "Place an order for a pet",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/order"
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
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "8797b365-50cb-4685-a5aa-08b59457dfaa",
            "name" : "Find purchase order by ID",
            "description" : "For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/order/{orderId}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "8ff2781d-396f-4714-a6b8-67ec7a00eebd",
            "name" : "Delete purchase order by ID",
            "description" : "For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/order/{orderId}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "b70fade5-835b-44b5-ad34-a2e2bcd0ddb2",
            "name" : "Returns pet inventories by status",
            "description" : "Returns a map of status codes to quantities",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/inventory"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : false,
              "name" : "api_key",
              "value" : "${\"Api_keyHeaderApi_key\"}"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form"
          }
        } ]
      }, {
        "entity" : {
          "type" : "Service",
          "name" : "User"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "98b9689c-2281-44fc-b4b9-adbcdcc5a27b",
            "name" : "Create user",
            "description" : "This can only be done by the logged in user.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user"
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
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "2e52d38d-daf0-49f0-90df-2d098b7547b5",
            "name" : "Creates list of users with given input array",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/createWithArray"
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
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "bbba5715-de17-4bbd-af17-2a19e36b892a",
            "name" : "Creates list of users with given input array",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/createWithList"
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
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "de06cd51-f22b-43d3-8a2d-6338492d5a98",
            "name" : "Get user by user name",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/{username}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "eef912c3-30fc-439d-8289-3d4872f222bf",
            "name" : "Updated user",
            "description" : "This can only be done by the logged in user.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/{username}"
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
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "adffa1c6-4925-4ded-ac17-4cd82a561846",
            "name" : "Delete user",
            "description" : "This can only be done by the logged in user.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/{username}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "1debb95c-d86c-4c42-972f-de4bbc15b8a1",
            "name" : "Logs user into the system",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/login",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "username",
                  "value" : "",
                  "enabled" : true
                }, {
                  "name" : "password",
                  "value" : "",
                  "enabled" : true
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
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "e2289a34-a738-4ea1-83fa-53545e4cf948",
            "name" : "Logs out current logged in user session",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/logout"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        } ]
      } ]
    } ],
    "environments" : [ {
      "name" : "Petstore API 4.1.0",
      "importedFrom" : {
        "projectId" : "4f8884b3-15cb-44a4-a518-16fe3e9956a3"
      },
      "variables" : {
        "a81706ad-8921-48e8-ad89-e702301dfb5b" : {
          "name" : "BaseUrl",
          "value" : "http://petstore.swagger.io/v2",
          "enabled" : true,
          "private" : false
        },
        "294c931a-83ef-46c8-b50f-5ecead9a1d38" : {
          "name" : "Api_keyHeaderApi_key",
          "value" : "",
          "enabled" : true,
          "private" : true
        }
      }
    } ]
  }
---
