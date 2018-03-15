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
  /{AccountId}/vaults/{VaultName}/multipart-uploads/{uploadID}:
    get:
      summary: List  Parts
      description: "DescriptionThis multipart upload operation lists the parts of
        an archive that have been uploaded in a\n\t\t\tspecific multipart upload identified
        by an upload ID"
      operationId: list Parts (GET uploadID)
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
        description: The ID of the upload to which the parts are associated
        type: string
      - in: query
        name: Parts
        description: A list of the part sizes of the multipart upload
        type: string
      - in: query
        name: PartSizeInBytes
        description: The part size in bytes
        type: string
      - in: query
        name: RangeInBytes
        description: The byte range of a part, inclusive of the upper value of the
          range
        type: string
      - in: query
        name: SHA256TreeHash
        description: The SHA256 tree hash value that Amazon Glacier calculated for
          the part
        type: string
      - in: query
        name: VaultARN
        description: "The Amazon Resource Name (ARN) of the vault to which the multipart\t\t\t\t\t\t\tupload
          was initiated"
        type: string
      responses:
        200:
          description: OK
      tags:
      - parts
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