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
    get:
      summary: Get  Vault  Lock
      description: "DescriptionThis operation retrieves the following attributes from
        the lock-policy\n\t\t\tsubresource set on the specified vault: \n\t\t\tThe
        vault lock policy set on the vault"
      operationId: Get Vault Lock (GET lock-policy)
      parameters:
      - in: query
        name: CreationDate
        description: "The UTC date and time at which the vault lock was put into the
          InProgress\t\t\t\t\t\t\tstate"
        type: string
      - in: query
        name: ExpirationDate
        description: The UTC date and time at which the lock ID expires
        type: string
      - in: query
        name: Policy
        description: The vault lock policy as a JSON string, which uses \ as an escape
          character
        type: string
      - in: query
        name: State
        description: The state of the vault lock
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