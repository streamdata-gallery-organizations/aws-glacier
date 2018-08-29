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
  /{AccountID}/vaults/{VaultName}/jobs/{JobID}:
    get:
      summary: Describe  Job
      description: "DescriptionThis operation returns information about a job you
        previously initiated, including the job\n\t\t\tinitiation date, the user who
        initiated the job, the job status code/message and the\n\t\t\tAmazon Simple
        Notification Service (Amazon SNS) topic to notify after Amazon Glacier\n\t\t\tcompletes
        the job"
      operationId: describe Job (GET JobID)
      parameters:
      - in: query
        name: Action
        description: The job type
        type: string
      - in: query
        name: ArchiveId
        description: For an ArchiveRetrieval job, this is the archive ID requested
          for download
        type: string
      - in: query
        name: ArchiveSHA256TreeHash
        description: The SHA256 tree hash of the entire archive for an archive retrieval
          job
        type: string
      - in: query
        name: ArchiveSizeInBytes
        description: "For an ArchiveRetrieval job, this is the size in bytes of the
          archive being\t\t\t\t\t\t\trequested for download"
        type: string
      - in: query
        name: Completed
        description: The job status
        type: string
      - in: query
        name: CompletionDate
        description: The UTC time that the job request completed
        type: string
      - in: query
        name: CreationDate
        description: The UTC time that the job was created
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
        description: "For an InventoryRetrieval job, this is the size in bytes of
          the inventory\t\t\t\t\t\t\trequested for download"
        type: string
      - in: query
        name: JobDescription
        description: The job description you provided when you initiated the job
        type: string
      - in: query
        name: JobId
        description: The ID that represents the job in Amazon Glacier
        type: string
      - in: query
        name: Limit
        description: "Specifies the maximum number of inventory items returned per
          vault inventory \t\t\t\t\t\t\tretrieval request"
        type: string
      - in: query
        name: Marker
        description: "An opaque string that represents where to continue pagination
          of the vault inventory\t\t\t\t\t\t\tretrieval results"
        type: string
      - in: query
        name: RetrievalByteRange
        description: "The retrieved byte range for archive retrieval jobs in the form\t\t\t\t\t\t\t\tStartByteValue-EndByteValue\t\t\t\t\t\t\tIf
          you don't specify a range in the archive retrieval, then the whole\t\t\t\t\t\t\tarchive
          is retrieved; also StartByteValue equals 0,\t\t\t\t\t\t\tand EndByteValue
          equals the size of the archive\t\t\t\t\t\t\tminus 1"
        type: string
      - in: query
        name: SHA256TreeHash
        description: The SHA256 tree hash value for the requested range of an archive
        type: string
      - in: query
        name: SNSTopic
        description: "An Amazon Simple Notification Service (Amazon SNS) topic that
          receives\t\t\t\t\t\t\tnotification"
        type: string
      - in: query
        name: StartDate
        description: "The start of the date range in UTC for vault inventory retrieval
          that includes archives\t\t\t\t\t\t\tcreated on or after this date"
        type: string
      - in: query
        name: StatusCode
        description: "The status code can be InProgress, Succeeded, or\t\t\t\t\t\t\t\tFailed,
          and indicates the status of the job"
        type: string
      - in: query
        name: StatusMessage
        description: A friendly message that describes the job status
        type: string
      - in: query
        name: Tier
        description: The retrieval option to use for the archive retrieval
        type: string
      - in: query
        name: VaultARN
        description: "The Amazon Resource Name (ARN) of the vault from which the archive\t\t\t\t\t\t\tretrieval
          was requested"
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