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
    get:
      summary: List  Jobs
      description: "DescriptionThis operation lists jobs for a vault including jobs
        that are in-progress and jobs that have\n\t\t\trecently finished"
      operationId: list Jobs (GET jobs)
      parameters:
      - in: query
        name: Action
        description: For archive retrieval jobs, this value is ArchiveRetrieval
        type: string
      - in: query
        name: ArchiveId
        description: The ID of the archive that was requested in an archive retrieval
        type: string
      - in: query
        name: ArchiveSHA256TreeHash
        description: The SHA256 tree hash of the entire archive for an archive retrieval
        type: string
      - in: query
        name: ArchiveSizeInBytes
        description: "The size of the archive for which the archive retrieval job
          request\t\t\t\t\t\t\twas initiated"
        type: string
      - in: query
        name: Completed
        description: true if the job is completed; false otherwise
        type: string
      - in: query
        name: CompletionDate
        description: The Universal Coordinated Time (UTC) date when the job completed
        type: string
      - in: query
        name: CreationDate
        description: The Universal Coordinated Time (UTC) date the job started
        type: string
      - in: query
        name: EndDate
        description: "The end of the date range in UTC for vault inventory retrieval
          that includes \t\t\t\t\t\t\tarchives created before this date"
        type: string
      - in: query
        name: Format
        description: "The output format for the vault inventory list, which is set
          by the  \t\t\t\t\t\t\tInitiate Job (POST jobs) request  \t\t\t\t\t\t\twhen
          initiating a job to retrieve a vault inventory"
        type: string
      - in: query
        name: InventorySizeInBytes
        description: The size of the inventory associated with an inventory retrieval
          job request
        type: string
      - in: query
        name: JobDescription
        description: A description of the job
        type: string
      - in: query
        name: JobId
        description: The ID that represents the job in Amazon Glacier
        type: string
      - in: query
        name: JobList
        description: An array of job objects
        type: string
      - in: query
        name: Limit
        description: "Specifies the maximum number of inventory items returned per
          vault inventory retrieval\t\t\t\t\t\t\trequest"
        type: string
      - in: query
        name: Marker
        description: An opaque string that represents where to continue pagination
          of the results
        type: string
      - in: query
        name: Marker (InventoryRetrievalParameters)
        description: "An opaque string that represents where to continue pagination
          of the vault inventory\t\t\t\t\t\t\tretrieval results"
        type: string
      - in: query
        name: RetrievalByteRange
        description: "The retrieved byte range for archive retrieval jobs in the form\t\t\t\t\t\t\t\tStartByteValue-EndByteValue\t\t\t\t\t\t\tIf
          no range was specified in the archive retrieval, then the whole\t\t\t\t\t\t\tarchive
          is retrieved and StartByteValue equals 0\t\t\t\t\t\t\tand EndByteValue equals
          the size of the archive\t\t\t\t\t\t\tminus 1"
        type: string
      - in: query
        name: SHA256TreeHash
        description: The SHA256 tree hash value for the requested range of an archive
        type: string
      - in: query
        name: SNSTopic
        description: "The Amazon Resource Name (ARN) that represents an Amazon SNS
          topic where notification of\t\t\t\t\t\t\tjob completion or failure is sent,
          if notification was configured in the\t\t\t\t\t\t\tjob initiation (Initiate
          Job (POST jobs))"
        type: string
      - in: query
        name: StartDate
        description: "The start of the date range in UTC for vault inventory retrieval
          that includes archives\t\t\t\t\t\t\tcreated on or after this date"
        type: string
      - in: query
        name: StatusCode
        description: The job status code
        type: string
      - in: query
        name: StatusMessage
        description: The job status message
        type: string
      - in: query
        name: Tier
        description: The retrieval option to use for the archive retrieval
        type: string
      - in: query
        name: VaultARN
        description: "The Amazon Resource Name (ARN) of the vault of which the job
          is a\t\t\t\t\t\t\tsubresource"
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