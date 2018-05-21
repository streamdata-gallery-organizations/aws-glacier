---
swagger: "2.0"
x-collection-name: AWS Glacier
x-complete: 0
info:
  title: Amazon Glacier API Set  Data  Retrieval  Policy
  version: 1.0.0
  description: "DescriptionThis operation sets and then enacts a data retrieval policy
    in the region specified in the PUT request. You can set one\n\t\t\tpolicy per
    region for an AWS account. The policy is enacted within a few minutes of a\n\t\t\tsuccessful
    PUT operation.  The set policy operation does not affect retrieval jobs that were
    in progress before the policy was\n\t\t\tenacted. For more information about data
    retrieval policies, see Amazon Glacier Data Retrieval Policies. Requests"
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