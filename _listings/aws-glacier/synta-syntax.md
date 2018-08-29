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
  Synta:
    syntax:
      summary: List  Provisioned  Capacity
      description: |-
        List Provisioned Capacity (GET
                provisioned-capacity)This operation lists the provisioned capacity for the specified AWS account
      operationId: |-
        List Provisioned Capacity (GET
                provisioned-capacity)
      parameters:
      - in: query
        name: CapacityId
        description: The ID that identifies the provisioned capacity unit
        type: string
      - in: query
        name: DryRun
        description: Checks whether you have the required permissions for the action,
          without actually making the request,        and provides an error response
        type: string
      - in: query
        name: ExpirationDate
        description: The date that the provisioned capacity unit expires, in Coordinated                            Universal
          Time (UTC)
        type: string
      - in: query
        name: Filter.N
        description: One or more filters
        type: string
      - in: query
        name: NetworkInterfaceId.N
        description: One or more network interface IDs
        type: string
      - in: query
        name: StartDate
        description: The date that the provisioned capacity unit was purchased, in
          Coordinated                            Universal Time (UTC)
        type: string
      - in: query
        name: TagKeys
        description: A list of tag keys
        type: string
      - in: query
        name: Tags
        description: The tags attached to the vault
        type: string
      responses:
        200:
          description: OK
      tags:
      - ""
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