---
swagger: "2.0"
x-collection-name: AWS Glacier
x-complete: 0
info:
  title: Amazon Glacier API Initiate  Job
  version: 1.0.0
  description: "Initiate Job (POST jobs)This operation initiates a job of the specified
    type, which can be an archive retrieval or vault inventory retrieval.Initializing
    a Data Retrieval Job Retrieving an archive or a vault inventory are asynchronous
    operations that require you to\n\t\t\tinitiate a job. Retrieval is a two-step
    process:\n\t\t\tInitiate a retrieval job.ImportantA data retrieval policy can
    cause your initiate retrieval job request to fail with a\n\t\t\t\t\t\t\t\tPolicyEnforcedException
    exception. For more information about data\n\t\t\t\t\t\t\tretrieval policies,
    see Amazon Glacier Data Retrieval Policies. For more information about the\n\t\t\t\t\t\t\t\tPolicyEnforcedException
    exception, see Error Responses.After the job completes, download the bytes. \n\t\tThe
    retrieval request is executed asynchronously. When you initiate a retrieval job,
    Amazon Glacier creates a job\n\t\t\tand returns a job ID in the response. When
    Amazon Glacier completes the job, you can get the job output (archive or\n\t\t\tinventory
    data). For information about getting job output, see the Get Job Output (GET output)
    operation. The job must complete before you can get its output. To determine when
    a job is complete, you have the\n\t\t\tfollowing options:\n\t\t\tUse an Amazon
    SNS notification&#8212; You can specify an Amazon Simple Notification Service\n\t\t\t\t\t\t(Amazon
    SNS) topic to which Amazon Glacier can post a notification after the job is completed.
    You can specify\n\t\t\t\t\t\tan SNS topic per job request. The notification is
    sent only after Amazon Glacier completes the job. In\n\t\t\t\t\t\taddition to
    specifying an SNS topic per job request, you can configure vault notifications
    for a\n\t\t\t\t\t\tvault so that job notifications are sent for all retrievals.
    For more information, see Set Vault Notification Configuration (PUT\n\t\tnotification-configuration).
    Get job details&#8212; You can make a Describe Job (GET JobID) request to obtain
    job\n\t\t\t\t\t\tstatus information while a job is in progress. However, it is
    more efficient to use an Amazon SNS\n\t\t\t\t\t\tnotification to determine when
    a job is complete.\n\t\t\n\t\t\tNoteThe information you get via notification is
    same that you get by calling Describe Job (GET JobID). \n\t\tIf for a specific
    event, you add both the notification configuration on the vault and also specify
    an SNS\n\t\t\ttopic in your initiate job request, Amazon Glacier sends both notifications.
    For more information, see Set Vault Notification Configuration (PUT\n\t\tnotification-configuration)."
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /{AccountId}/vaults/{VaultName}/archives:
    post:
      summary: Upload  Archive
      description: "DescriptionThis operation adds an archive to a vault. For a successful
        upload, your data is durably\n\t\t\tpersisted. In response, Amazon Glacier
        returns the archive ID in the\n\t\t\t\tx-amz-archive-id header of the response.
        You should save the archive ID\n\t\t\treturned so that you can access the
        archive later. You must provide a SHA256 tree hash of the data you are uploading.
        For information about\n\t\t\tcomputing a SHA256 tree hash, see Computing Checksums.
        When uploading an archive, you can optionally specify an archive description
        of up to 1,024\n\t\t\tprintable ASCII characters. Amazon Glacier returns the
        archive description when you\n\t\t\teither retrieve the archive or get the
        vault inventory. Amazon Glacier does not interpret the\n\t\t\tdescription
        in any way. An archive description does not need to be unique. You cannot\n\t\t\tuse
        the description to retrieve or sort the archive list. Except for the optional
        archive description, Amazon Glacier does not support any\n\t\t\tadditional
        metadata for the archives. The archive ID is an opaque sequence of characters\n\t\t\tfrom
        which you cannot infer any meaning about the archive. So you might maintain\n\t\t\tmetadata
        about the archives on the client-side. For more information, see \n\t\t\tWorking
        with Archives in Amazon Glacier.Archives are immutable. After you upload an
        archive, you cannot edit the archive or its\n\t\t\tdescription. RequestsTo
        upload an archive, you use the HTTP POST method and scope the request to the\n\t\t\t\tarchives
        subresource of the vault in which you want to save the\n\t\t\tarchive. The
        request must include the archive payload size, checksum (SHA256 tree hash),\n\t\t\tand
        can optionally include a description of the archive."
      operationId: Upload Archive (POST archive)
      x-api-path-slug: accountidvaultsvaultnamearchives-post
      parameters:
      - type: string
      responses:
        200:
          description: OK
      tags:
      - Archives
  /{AccountId}/policies/data-retrieval:
    get:
      summary: Get  Data  Retrieval  Policy
      description: "DescriptionThis operation returns the current data retrieval policy
        for the account and region specified in the\n\t\t\t\tGET request. For more
        information about data retrieval policies, see\n\t\t\tAmazon Glacier Data
        Retrieval Policies.RequestsTo return the current data retrieval policy, send
        an HTTP GET request to the data retrieval\n\t\t\tpolicy URI as shown in the
        following syntax example."
      operationId: Get Data Retrieval Policy (GET policy)
      x-api-path-slug: accountidpoliciesdataretrieval-get
      parameters:
      - in: query
        name: BytesPerHour
        description: The maximum number of bytes that can be retrieved in an hour
        type: string
      - in: query
        name: Rules
        description: The policy rule
        type: string
      - in: query
        name: Strategy
        description: The type of data retrieval policy
        type: string
      responses:
        200:
          description: OK
      tags:
      - Data  Retrieval  Policies
    put:
      summary: Set  Data  Retrieval  Policy
      description: "DescriptionThis operation sets and then enacts a data retrieval
        policy in the region specified in the PUT request. You can set one\n\t\t\tpolicy
        per region for an AWS account. The policy is enacted within a few minutes
        of a\n\t\t\tsuccessful PUT operation.  The set policy operation does not affect
        retrieval jobs that were in progress before the policy was\n\t\t\tenacted.
        For more information about data retrieval policies, see Amazon Glacier Data
        Retrieval Policies. Requests"
      operationId: Set Data Retrieval Policy (PUT policy)
      x-api-path-slug: accountidpoliciesdataretrieval-put
      parameters:
      - in: query
        name: BytesPerHour
        description: The maximum number of bytes that can be retrieved in an hour
        type: string
      - in: query
        name: Rules
        description: The policy rule
        type: string
      - in: query
        name: Strategy
        description: The type of data retrieval policy to set
        type: string
      responses:
        200:
          description: OK
      tags:
      - Data  Retrieval  Policy
  /{AccountId}/provisioned-capacity:
    post:
      summary: Purchase  Provisioned  Capacity
      description: |-
        Purchase Provisioned Capacity (POST provisioned-capacity)This operation purchases a provisioned capacity unit for an AWS account.RequestsTo purchase provisioned capacity unit for an AWS account send an HTTP POST
                 request to the provisioned-capacity URI.
      operationId: Purchase Provisioned Capacity (POST provisioned-capacity)
      x-api-path-slug: accountidprovisionedcapacity-post
      parameters:
      - type: string
      responses:
        200:
          description: OK
      tags:
      - Purchase Provisioned Capacity
  /{AccountID}/vaults/{VaultName}/jobs/{JobID}:
    get:
      summary: Describe  Job
      description: "DescriptionThis operation returns information about a job you
        previously initiated, including the job\n\t\t\tinitiation date, the user who
        initiated the job, the job status code/message and the\n\t\t\tAmazon Simple
        Notification Service (Amazon SNS) topic to notify after Amazon Glacier\n\t\t\tcompletes
        the job. For more information about initiating a job, see Initiate Job (POST
        jobs). \n\t\t\tNoteThis operation enables you to check the status of your
        job. However, it is\n\t\t\t\t\tstrongly recommended that you set up an Amazon
        SNS topic and specify it in your\n\t\t\t\t\tinitiate job request so that Amazon
        Glacier can notify the topic after it completes\n\t\t\t\t\tthe job. \n\t\tA
        job ID will not expire for at least 24 hours after Amazon Glacier completes
        the job. Requests"
      operationId: describe Job (GET JobID)
      x-api-path-slug: accountidvaultsvaultnamejobsjobid-get
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
        description: For an ArchiveRetrieval job, this is the size in bytes of the
          archive beingrequested for download
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
        description: The end of the date range in UTC for vault inventory retrieval
          that includes archives created before this date
        type: string
      - in: query
        name: Format
        description: The output format for the vault inventory list, which is set
          by the  Initiate Job (POST jobs) request  when initiating a job to retrieve
          a vault inventory
        type: string
      - in: query
        name: InventorySizeInBytes
        description: For an InventoryRetrieval job, this is the size in bytes of the
          inventoryrequested for download
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
        description: Specifies the maximum number of inventory items returned per
          vault inventory retrieval request
        type: string
      - in: query
        name: Marker
        description: An opaque string that represents where to continue pagination
          of the vault inventoryretrieval results
        type: string
      - in: query
        name: RetrievalByteRange
        description: The retrieved byte range for archive retrieval jobs in the formStartByteValue-EndByteValueIf
          you dont specify a range in the archive retrieval, then the wholearchive
          is retrieved; also StartByteValue equals 0,and EndByteValue equals the size
          of the archiveminus 1
        type: string
      - in: query
        name: SHA256TreeHash
        description: The SHA256 tree hash value for the requested range of an archive
        type: string
      - in: query
        name: SNSTopic
        description: An Amazon Simple Notification Service (Amazon SNS) topic that
          receivesnotification
        type: string
      - in: query
        name: StartDate
        description: The start of the date range in UTC for vault inventory retrieval
          that includes archivescreated on or after this date
        type: string
      - in: query
        name: StatusCode
        description: The status code can be InProgress, Succeeded, orFailed, and indicates
          the status of the job
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
        description: The Amazon Resource Name (ARN) of the vault from which the archiveretrieval
          was requested
        type: string
      responses:
        200:
          description: OK
      tags:
      - Jobs
  /{AccountId}/vaults/{VaultName}/jobs/{JobID}/output:
    get:
      summary: Get  Job  Output
      description: "DescriptionThis operation downloads the output of the job you
        initiated using Initiate Job (POST jobs). Depending\n\t\t\ton the job type
        you specified when you initiated the job, the output will be either the\n\t\t\tcontent
        of an archive or a vault inventory. You can download all the job output or
        download a portion of the output by specifying\n\t\t\ta byte range. For both
        archive and inventory retrieval jobs, you should verify the downloaded \n\t\t\tsize
        against the size returned in the headers from the \n\t\t\tGet Job Output response.For
        archive retrieval jobs, you should also verify that the size is what you expected.
        If\n\t\t\tyou download a portion of the output, the expected size is based
        on the range of bytes\n\t\t\tyou specified. For example, if you specify a
        range of bytes=0-1048575, you should\n\t\t\tverify your download size is 1,048,576
        bytes. If you download an entire archive, the\n\t\t\texpected size is the
        size of the archive when you uploaded it to Amazon Glacier.\n\t\t\tThe expected
        size is also returned in the headers from the \n\t\t\tGet Job Output response.In
        the case of an archive retrieval job, depending on the byte range you\n\t\t\tspecify,
        Amazon Glacier returns the checksum for the portion of the data. To ensure
        the portion you downloaded \n\t\t\tis the correct data, compute the checksum
        on the client, verify that the values match, \n\t\t\tand verify that the size
        is what you expected.A job ID does not expire for at least 24 hours after
        Amazon Glacier completes the job. That\n\t\t\tis, you can download the job
        output within the 24-hour period after Amazon Glacier\n\t\t\tcompletes the
        job.Requests"
      operationId: get Job Output (GET output)
      x-api-path-slug: accountidvaultsvaultnamejobsjobidoutput-get
      parameters:
      - type: string
      - in: query
        name: ArchiveDescription
        description: The description of an archive
        type: string
      - in: query
        name: ArchiveId
        description: The ID of an archive
        type: string
      - in: query
        name: ArchiveList
        description: An array of archive metadata
        type: string
      - in: query
        name: CreationDate
        description: The UTC date and time the archive was created
        type: string
      - in: query
        name: InventoryDate
        description: The UTC date and time of the last inventory for the vault that
          was completed afterchanges to the vault
        type: string
      - in: query
        name: SHA256TreeHash
        description: The tree hash of the archive
        type: string
      - in: query
        name: Size
        description: The size in bytes of the archive
        type: string
      - in: query
        name: VaultARN
        description: The Amazon Resource Name (ARN) resource from which the archiveretrieval
          was requested
        type: string
      responses:
        200:
          description: OK
      tags:
      - Jobs
  /{AccountId}/vaults/{VaultName}/jobs:
    post:
      summary: Initiate  Job
      description: "Initiate Job (POST jobs)This operation initiates a job of the
        specified type, which can be an archive retrieval or vault inventory retrieval.Initializing
        a Data Retrieval Job Retrieving an archive or a vault inventory are asynchronous
        operations that require you to\n\t\t\tinitiate a job. Retrieval is a two-step
        process:\n\t\t\tInitiate a retrieval job.ImportantA data retrieval policy
        can cause your initiate retrieval job request to fail with a\n\t\t\t\t\t\t\t\tPolicyEnforcedException
        exception. For more information about data\n\t\t\t\t\t\t\tretrieval policies,
        see Amazon Glacier Data Retrieval Policies. For more information about the\n\t\t\t\t\t\t\t\tPolicyEnforcedException
        exception, see Error Responses.After the job completes, download the bytes.
        \n\t\tThe retrieval request is executed asynchronously. When you initiate
        a retrieval job, Amazon Glacier creates a job\n\t\t\tand returns a job ID
        in the response. When Amazon Glacier completes the job, you can get the job
        output (archive or\n\t\t\tinventory data). For information about getting job
        output, see the Get Job Output (GET output) operation. The job must complete
        before you can get its output. To determine when a job is complete, you have
        the\n\t\t\tfollowing options:\n\t\t\tUse an Amazon SNS notification&#8212;
        You can specify an Amazon Simple Notification Service\n\t\t\t\t\t\t(Amazon
        SNS) topic to which Amazon Glacier can post a notification after the job is
        completed. You can specify\n\t\t\t\t\t\tan SNS topic per job request. The
        notification is sent only after Amazon Glacier completes the job. In\n\t\t\t\t\t\taddition
        to specifying an SNS topic per job request, you can configure vault notifications
        for a\n\t\t\t\t\t\tvault so that job notifications are sent for all retrievals.
        For more information, see Set Vault Notification Configuration (PUT\n\t\tnotification-configuration).
        Get job details&#8212; You can make a Describe Job (GET JobID) request to
        obtain job\n\t\t\t\t\t\tstatus information while a job is in progress. However,
        it is more efficient to use an Amazon SNS\n\t\t\t\t\t\tnotification to determine
        when a job is complete.\n\t\t\n\t\t\tNoteThe information you get via notification
        is same that you get by calling Describe Job (GET JobID). \n\t\tIf for a specific
        event, you add both the notification configuration on the vault and also specify
        an SNS\n\t\t\ttopic in your initiate job request, Amazon Glacier sends both
        notifications. For more information, see Set Vault Notification Configuration
        (PUT\n\t\tnotification-configuration)."
      operationId: initiate Job (POST jobs)
      x-api-path-slug: accountidvaultsvaultnamejobs-post
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
        description: The end of the date range in UTC for vault inventory retrieval
          that includes archivescreated before this date
        type: string
      - in: query
        name: Format
        description: When initiating a job to retrieve a vault inventory, you can
          optionally add this parameterto your request to specify the output format
        type: string
      - in: query
        name: Limit
        description: The maximum number of inventory items returned per vault inventory
          retrievalrequest
        type: string
      - in: query
        name: Marker
        description: An opaque string that represents where to continue pagination
          of the vault inventoryretrieval results
        type: string
      - in: query
        name: RetrievalByteRange
        description: The byte range to retrieve for an archive retrieval
        type: string
      - in: query
        name: SNSTopic
        description: The Amazon SNS topic ARN where Amazon Glacier sends a notification
          when the job is completed, and theoutput is ready for you to download
        type: string
      - in: query
        name: StartDate
        description: The start of the date range in UTC for vault inventory retrieval
          that includes archivescreated on or after this date
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
      - Jobs
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