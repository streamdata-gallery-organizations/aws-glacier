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
  /{AccountId}/vaults/{VaultName}/jobs:
    post:
      summary: Initiate  Job
      description: Initiate Job (POST jobs)This operation initiates a job of the specified
        type, which can be an archive retrieval or vault inventory retrieval
      operationId: initiate Job (POST jobs)
      parameters:
      - type: string
      - in: query
        name: ArchiveId
        description: The ID of the archive that you want to retrieve
        type: string
      - in: query
        name: Description
        description: The optional description for the job
        type: string
      - in: query
        name: EndDate
        description: "The end of the date range in UTC for vault inventory retrieval
          that includes archives\t\t\t\t\t\t\tcreated before this date"
        type: string
      - in: query
        name: Format
        description: "When initiating a job to retrieve a vault inventory, you can
          optionally add this parameter\t\t\t\t\t\t\tto your request to specify the
          output format"
        type: string
      - in: query
        name: Limit
        description: "The maximum number of inventory items returned per vault inventory
          retrieval\t\t\t\t\t\t\trequest"
        type: string
      - in: query
        name: Marker
        description: "An opaque string that represents where to continue pagination
          of the vault inventory\t\t\t\t\t\t\tretrieval results"
        type: string
      - in: query
        name: RetrievalByteRange
        description: The byte range to retrieve for an archive retrieval
        type: string
      - in: query
        name: SNSTopic
        description: "The Amazon SNS topic ARN where Amazon Glacier sends a notification
          when the job is completed, and the\t\t\t\t\t\t\toutput is ready for you
          to download"
        type: string
      - in: query
        name: StartDate
        description: "The start of the date range in UTC for vault inventory retrieval
          that includes archives\t\t\t\t\t\t\tcreated on or after this date"
        type: string
      - in: query
        name: Tier
        description: The retrieval option to use for the archive retrieval
        type: string
      - in: query
        name: Type
        description: The job type
        type: string
      responses:
        200:
          description: OK
      tags:
      - jobs
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