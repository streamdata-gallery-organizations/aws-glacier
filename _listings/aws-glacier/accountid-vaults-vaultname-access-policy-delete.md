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
  /{AccountId}/vaults/{vaultName}/access-policy:
    delete:
      summary: Delete  Vault  Access  Policy
      description: DescriptionThis operation deletes the access policy associated
        with the specified vault
      operationId: "Delete Vault Access Policy (DELETE\n\t\taccess-policy)"
      responses:
        200:
          description: OK
      tags:
      - vault access policies
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