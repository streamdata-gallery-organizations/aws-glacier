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
  /{AccountId}/vaults/{vaultName}/lock-policy:
    post:
      summary: Initiate  Vault  Lock
      description: 'DescriptionThis operation initiates the vault locking process
        by doing the following: Installing a vault lock policy on the specified vault'
      operationId: Initiate Vault Lock (POST lock-policy)
      parameters:
      - type: string
      - in: query
        name: Policy
        description: "The vault lock policy as a JSON string, which uses \\ as an
          escape\t\t\t\t\t\t\tcharacter"
        type: string
      responses:
        200:
          description: OK
      tags:
      - vault locks
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