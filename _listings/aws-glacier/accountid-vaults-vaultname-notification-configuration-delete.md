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
    delete:
      summary: Delete  Vault  Notifications
      description: "DescriptionThis operation deletes the notification configuration
        set for a vault \n\t\t\tSet Vault Notification Configuration (PUT\n\t\tnotification-configuration)"
      operationId: "Delete Vault Notifications (DELETE\n\t\tnotification-configuration)"
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