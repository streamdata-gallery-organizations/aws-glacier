---
swagger: "2.0"
info:
  title: AWS Glacier API
  version: 1.0.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /{AccountId}/policies/data-retrieval:
    get:
      summary: Get  Data  Retrieval  Policy
      description: "DescriptionThis operation returns the current data retrieval policy
        for the account and region specified in the\n\t\t\t\tGET request"
      operationId: Get Data Retrieval Policy (GET policy)
      parameters:
      - in: query
        name: BytesPerHour
        description: The maximum number of bytes that can be retrieved in an hour
        type: string
      - in: query
        name: Rules
        description: The policy rule
        type: string
      - in: query
        name: Strategy
        description: The type of data retrieval policy
        type: string
      responses:
        200:
          description: OK
      tags:
      - data  retrieval  policies
definitions: []
x-collection-name: AWS Glacier
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---