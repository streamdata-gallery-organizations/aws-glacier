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
  /{AccountId}/vaults/{VaultName}/notification-configuration:
    put:
      summary: Set  Vault  Notification  Configuration
      description: "DescriptionRetrieving an archive and a vault inventory are asynchronous
        operations in Amazon Glacier for which\n\t\t\tyou must first initiate a job
        and wait for the job to complete before you can download\n\t\t\tthe job output"
      operationId: "Set Vault Notification Configuration (PUT\n\t\tnotification-configuration)"
      parameters:
      - in: query
        name: Events
        description: "An array of one or more events for which you want Amazon Glacier
          to send\t\t\t\t\t\t\tnotification"
        type: string
      - in: query
        name: SNSTopic
        description: The Amazon SNS topic ARN
        type: string
      responses:
        200:
          description: OK
      tags:
      - vault notifications
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