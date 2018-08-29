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
  /{AccountId}/vaults/{vaultName}/lock-policy/{lockId}:
    post:
      summary: Complete  Vault  Lock
      description: |-
        DescriptionThis operation completes the vault locking process by transitioning the vault lock from
                 the InProgress state to the Locked state, which causes the vault
                 lock policy to become unchangeable
      operationId: Complete Vault Lock (POST lockId)
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