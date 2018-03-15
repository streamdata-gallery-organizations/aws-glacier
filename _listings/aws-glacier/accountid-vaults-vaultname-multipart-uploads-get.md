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
  /{AccountId}/vaults/{VaultName}/multipart-uploads:
    get:
      summary: List  Multipart  Uploads
      description: DescriptionThis multipart upload operation lists in-progress multipart
        uploads for the specified vault
      operationId: list Multipart Uploads (GET multipart-uploads)
      parameters:
      - in: query
        name: ArchiveDescription
        description: "The description of the archive that was specified in the Initiate
          Multipart Upload\t\t\t\t\t\t\trequest"
        type: string
      - in: query
        name: CreationDate
        description: The UTC time that the multipart upload was initiated
        type: string
      - in: query
        name: Marker
        description: An opaque string that represents where to continue pagination
          of the results
        type: string
      - in: query
        name: MultipartUploadId
        description: The ID of the multipart upload
        type: string
      - in: query
        name: PartSizeInBytes
        description: "The part size specified in the Initiate Multipart Upload (POST\t\tmultipart-uploads)
          request"
        type: string
      - in: query
        name: UploadsList
        description: A list of metadata about multipart upload objects
        type: string
      - in: query
        name: VaultARN
        description: The Amazon Resource Name (ARN) of the vault that contains the
          archive
        type: string
      responses:
        200:
          description: OK
      tags:
      - multipart uploads
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