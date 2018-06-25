---
name: AWS Glacier
x-slug: aws-glacier
description: Amazon Glacier is a secure, durable, and extremely low-cost cloud storage
  service for data archiving and long-term backup. Customers can reliably store large
  or small amounts of data for as little as $0.004 per gigabyte per month, a significant
  savings compared to on-premises solutions. To keep costs low yet suitable for varying
  retrieval needs, Amazon Glacier provides three options for access to archives, from
  a few minutes to several hours.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
x-kinRank: "10"
x-alexaRank: "0"
tags: AWS Glacier
created: "2018-06-25"
modified: "2018-06-25"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/apis.md
specificationVersion: "0.14"
apis:
- name: Amazon Glacier API Upload  Archive
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation adds an archive to a vault. For a successful
    upload, your data is durably\n\t\t\tpersisted. In response, Amazon Glacier returns
    the archive ID in the\n\t\t\t\tx-amz-archive-id header of the response. You should
    save the archive ID\n\t\t\treturned so that you can access the archive later.
    You must provide a SHA256 tree hash of the data you are uploading. For information
    about\n\t\t\tcomputing a SHA256 tree hash, see Computing Checksums. When uploading
    an archive, you can optionally specify an archive description of up to 1,024\n\t\t\tprintable
    ASCII characters. Amazon Glacier returns the archive description when you\n\t\t\teither
    retrieve the archive or get the vault inventory. Amazon Glacier does not interpret
    the\n\t\t\tdescription in any way. An archive description does not need to be
    unique. You cannot\n\t\t\tuse the description to retrieve or sort the archive
    list. Except for the optional archive description, Amazon Glacier does not support
    any\n\t\t\tadditional metadata for the archives. The archive ID is an opaque sequence
    of characters\n\t\t\tfrom which you cannot infer any meaning about the archive.
    So you might maintain\n\t\t\tmetadata about the archives on the client-side. For
    more information, see \n\t\t\tWorking with Archives in Amazon Glacier.Archives
    are immutable. After you upload an archive, you cannot edit the archive or its\n\t\t\tdescription.
    RequestsTo upload an archive, you use the HTTP POST method and scope the request
    to the\n\t\t\t\tarchives subresource of the vault in which you want to save the\n\t\t\tarchive.
    The request must include the archive payload size, checksum (SHA256 tree hash),\n\t\t\tand
    can optionally include a description of the archive."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/archives
  tags: Archives
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamearchives-post-openapi.md
- name: Amazon Glacier API Get  Data  Retrieval  Policy
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation returns the current data retrieval policy
    for the account and region specified in the\n\t\t\t\tGET request. For more information
    about data retrieval policies, see\n\t\t\tAmazon Glacier Data Retrieval Policies.RequestsTo
    return the current data retrieval policy, send an HTTP GET request to the data
    retrieval\n\t\t\tpolicy URI as shown in the following syntax example."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/policies/data-retrieval
  tags: Data  Retrieval  Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidpoliciesdataretrieval-get-openapi.md
- name: Amazon Glacier API Purchase  Provisioned  Capacity
  x-api-slug: amazon-glacier-api
  description: |-
    Purchase Provisioned Capacity (POST provisioned-capacity)This operation purchases a provisioned capacity unit for an AWS account.RequestsTo purchase provisioned capacity unit for an AWS account send an HTTP POST
             request to the provisioned-capacity URI.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/provisioned-capacity
  tags: Purchase Provisioned Capacity
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidprovisionedcapacity-post-openapi.md
- name: Amazon Glacier API Set  Data  Retrieval  Policy
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation sets and then enacts a data retrieval policy
    in the region specified in the PUT request. You can set one\n\t\t\tpolicy per
    region for an AWS account. The policy is enacted within a few minutes of a\n\t\t\tsuccessful
    PUT operation.  The set policy operation does not affect retrieval jobs that were
    in progress before the policy was\n\t\t\tenacted. For more information about data
    retrieval policies, see Amazon Glacier Data Retrieval Policies. Requests"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/policies/data-retrieval
  tags: Data  Retrieval  Policy
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidpoliciesdataretrieval-put-openapi.md
- name: Amazon Glacier API Describe  Job
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation returns information about a job you previously
    initiated, including the job\n\t\t\tinitiation date, the user who initiated the
    job, the job status code/message and the\n\t\t\tAmazon Simple Notification Service
    (Amazon SNS) topic to notify after Amazon Glacier\n\t\t\tcompletes the job. For
    more information about initiating a job, see Initiate Job (POST jobs). \n\t\t\tNoteThis
    operation enables you to check the status of your job. However, it is\n\t\t\t\t\tstrongly
    recommended that you set up an Amazon SNS topic and specify it in your\n\t\t\t\t\tinitiate
    job request so that Amazon Glacier can notify the topic after it completes\n\t\t\t\t\tthe
    job. \n\t\tA job ID will not expire for at least 24 hours after Amazon Glacier
    completes the job. Requests"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountID}/vaults/{VaultName}/jobs/{JobID}
  tags: Jobs
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamejobsjobid-get-openapi.md
- name: Amazon Glacier API Get  Job  Output
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation downloads the output of the job you initiated
    using Initiate Job (POST jobs). Depending\n\t\t\ton the job type you specified
    when you initiated the job, the output will be either the\n\t\t\tcontent of an
    archive or a vault inventory. You can download all the job output or download
    a portion of the output by specifying\n\t\t\ta byte range. For both archive and
    inventory retrieval jobs, you should verify the downloaded \n\t\t\tsize against
    the size returned in the headers from the \n\t\t\tGet Job Output response.For
    archive retrieval jobs, you should also verify that the size is what you expected.
    If\n\t\t\tyou download a portion of the output, the expected size is based on
    the range of bytes\n\t\t\tyou specified. For example, if you specify a range of
    bytes=0-1048575, you should\n\t\t\tverify your download size is 1,048,576 bytes.
    If you download an entire archive, the\n\t\t\texpected size is the size of the
    archive when you uploaded it to Amazon Glacier.\n\t\t\tThe expected size is also
    returned in the headers from the \n\t\t\tGet Job Output response.In the case of
    an archive retrieval job, depending on the byte range you\n\t\t\tspecify, Amazon
    Glacier returns the checksum for the portion of the data. To ensure the portion
    you downloaded \n\t\t\tis the correct data, compute the checksum on the client,
    verify that the values match, \n\t\t\tand verify that the size is what you expected.A
    job ID does not expire for at least 24 hours after Amazon Glacier completes the
    job. That\n\t\t\tis, you can download the job output within the 24-hour period
    after Amazon Glacier\n\t\t\tcompletes the job.Requests"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/jobs/{JobID}/output
  tags: Jobs
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamejobsjobidoutput-get-openapi.md
- name: Amazon Glacier API Initiate  Job
  x-api-slug: amazon-glacier-api
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/jobs
  tags: Jobs
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamejobs-post-openapi.md
- name: Amazon Glacier API List  Jobs
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation lists jobs for a vault including jobs that
    are in-progress and jobs that have\n\t\t\trecently finished. \n\t\t\tNoteAmazon
    Glacier retains recently completed jobs for a period before deleting them; however,\n\t\t\t\t\tit
    eventually removes completed jobs. The output of completed jobs can be\n\t\t\t\t\tretrieved.
    Retaining completed jobs for a period of time after they have\n\t\t\t\t\tcompleted
    enables you to get a job output in the event you miss the job\n\t\t\t\t\tcompletion
    notification or your first attempt to download it fails. For example,\n\t\t\t\t\tsuppose
    you start an archive retrieval job to download an archive. After the job\n\t\t\t\t\tcompletes,
    you start to download the archive but encounter a network error. In\n\t\t\t\t\tthis
    scenario, you can retry and download the archive while the job exists. \n\t\tTo
    retrieve an archive or retrieve a vault inventory from Amazon Glacier, you first
    initiate\n\t\t\ta job, and after the job completes, you download the data. For
    an archive retrieval, the\n\t\t\toutput is the archive data. For an inventory
    retrieval, it is the inventory list.\n\t\t\tThe List Job operation returns a list
    of these jobs sorted by job initiation\n\t\t\ttime.The List Jobs operation supports
    pagination. You should always check the response\n\t\t\t\tMarker field. If there
    are no more jobs to list, the\n\t\t\t\tMarker field is set to null. If there are
    more jobs to\n\t\t\tlist, the Marker field is set to a non-null value, which you
    can use to\n\t\t\tcontinue the pagination of the list. To return a list of jobs
    that begins at a specific\n\t\t\tjob, set the marker request parameter to the
    Marker value for\n\t\t\tthat job that you obtained from a previous List Jobs request.You
    can set a maximum limit for the number of jobs returned in the response by specifying\n\t\t\tthe
    limit parameter in the request. The default limit is 1000. The number\n\t\t\tof
    jobs returned might be fewer than the limit but the number of returned jobs never\n\t\t\texceeds
    the limit.Additionally, you can filter the jobs list returned by specifying the
    optional\n\t\t\tstatuscode parameter or completed parameter, or both. Using\n\t\t\tthe
    statuscode parameter, you can specify to return only jobs that match\n\t\t\teither
    the InProgress, Succeeded, or Failed status.\n\t\t\tUsing the completed parameter,
    you can specify to return only jobs that were\n\t\t\tcompleted (true) or jobs
    that were not completed\n\t\t\t(false).Requests"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/jobs
  tags: Jobs
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamejobs-get-openapi.md
- name: Amazon Glacier API Abort  Multipart  Upload
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis multipart upload operation aborts a multipart upload
    identified by the upload\n\t\t\tID"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/multipart-uploads/{uploadID}
  tags: Multipart Uploads
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamemultipartuploadsuploadid-delete-openapi.md
- name: Amazon Glacier API Complete  Multipart  Upload
  x-api-slug: amazon-glacier-api
  description: "DescriptionYou call this multipart upload operation to inform Amazon
    Glacier that all the archive parts have\n\t\t\tbeen uploaded and Amazon Glacier
    can now assemble the archive from the uploaded parts"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/multipart-uploads/{uploadID}
  tags: Multipart Uploads
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamemultipartuploadsuploadid-post-openapi.md
- name: Amazon Glacier API List  Parts
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis multipart upload operation lists the parts of an archive
    that have been uploaded in a\n\t\t\tspecific multipart upload identified by an
    upload ID"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/multipart-uploads/{uploadID}
  tags: Parts
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamemultipartuploadsuploadid-get-openapi.md
- name: Amazon Glacier API List  Multipart  Uploads
  x-api-slug: amazon-glacier-api
  description: DescriptionThis multipart upload operation lists in-progress multipart
    uploads for the specified vault
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/multipart-uploads
  tags: Multipart Uploads
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamemultipartuploads-get-openapi.md
- name: Amazon Glacier API Upload  Part
  x-api-slug: amazon-glacier-api
  description: DescriptionThis multipart upload operation uploads a part of an archive
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/multipart-uploads/{uploadID}
  tags: Parts
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamemultipartuploadsuploadid-put-openapi.md
- name: Amazon Glacier API Abort  Vault  Lock
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation aborts the vault locking process if the
    vault lock is not in the\n\t\t\t\tLocked state. If the vault lock is in the Locked
    state\n\t\t\twhen this operation is requested, the operation returns an\n\t\t\t\tAccessDeniedException
    error. Aborting the vault locking process removes\n\t\t\tthe vault lock policy
    from the specified vault. A vault lock is put into the InProgress state by calling
    Initiate Vault Lock (POST lock-policy). A vault\n\t\t\tlock is put into the Locked
    state by calling Complete Vault Lock (POST lockId). You can\n\t\t\tget the state
    of a vault lock by calling Get Vault Lock (GET lock-policy). For more information
    about the vault\n\t\t\tlocking process, see Amazon Glacier Vault Lock. For more\n\t\t\tinformation
    about vault lock policies, see Amazon Glacier Access Control with Vault Lock Policies.This
    operation is idempotent. You can successfully invoke this operation multiple times,
    if\n\t\t\tthe vault lock is in the InProgress state or if there is no policy\n\t\t\tassociated
    with the vault.RequestsTo delete the vault lock policy, send an HTTP DELETE request
    to the URI\n\t\t\tof the vault's lock-policy subresource."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{vaultName}/lock-policy
  tags: Vault Locks
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamelockpolicy-delete-openapi.md
- name: Amazon Glacier API Create  Vault
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation creates a new vault with the specified name.&nbsp;
    The name of the vault must be\n\t\t\tunique within a region for an AWS account.
    You can create up to 1,000 vaults per\n\t\t\taccount. For information on creating
    more vaults, go to the Amazon Glacier product detail\n\t\t\tpage.You must use
    the following guidelines when naming a vault. \n\t\t\t Names can be between 1
    and 255 characters long. Allowed characters are a&#8211;z, A&#8211;Z, 0&#8211;9,
    '_' (underscore), '-' (hyphen),\n\t\t\t\t\t\tand '.' (period).\n\t\tThis operation
    is idempotent, you can send the same request multiple times and it has no\n\t\t\tfurther
    effect after the first time Amazon Glacier creates the specified vault.Requests"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}
  tags: Vaults
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultname-put-openapi.md
- name: Amazon Glacier API Complete  Vault  Lock
  x-api-slug: amazon-glacier-api
  description: |-
    DescriptionThis operation completes the vault locking process by transitioning the vault lock from
             the InProgress state to the Locked state, which causes the vault
             lock policy to become unchangeable. A vault lock is put into the InProgress
             state by calling Initiate Vault Lock (POST lock-policy). You can obtain the state of the vault lock by
             calling Get Vault Lock (GET lock-policy). For more
             information about the vault locking process, see Amazon Glacier Vault Lock. This operation is idempotent. This request is always successful if the vault lock is in the
             Locked state and the provided lock ID matches the lock ID originally used to
             lock the vault.If an invalid lock ID is passed in the request when the vault lock is in the Locked state,
             the operation returns an AccessDeniedException error. If an invalid lock ID is
             passed in the request when the vault lock is in the InProgress state, the operation throws an
                InvalidParameter error.RequestsTo complete the vault locking process, send an HTTP POST request to the URI
             of the vault's lock-policy subresource with a valid lock ID.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{vaultName}/lock-policy/{lockId}
  tags: Vault Locks
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamelockpolicylockid-post-openapi.md
- name: Amazon Glacier API Delete  Vault
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation deletes a vault. Amazon Glacier will delete
    a vault only if there are no archives\n\t\t\tin the vault as per the last inventory
    and there have been no writes to the vault since\n\t\t\tthe last inventory. If
    either of these conditions is not satisfied, the vault deletion\n\t\t\tfails (that
    is, the vault is not removed) and Amazon Glacier returns an error. You can use
    the Describe Vault (GET vault)\n\t\t\toperation that provides vault information,
    including the number of archives in the vault;\n\t\t\thowever, the information
    is based on the vault inventory Amazon Glacier last\n\t\t\tgenerated.This operation
    is idempotent.NoteWhen you delete a vault, the vault access policy attached to
    the vault is also deleted. \n\t\t\t\tFor more information about vault access policies,
    see Amazon Glacier Access Control with Vault Access Policies.RequestsTo delete
    a vault, send a DELETE request to the vault resource URI."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}
  tags: Vaults
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultname-delete-openapi.md
- name: Amazon Glacier API Delete  Vault  Access  Policy
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation deletes the access policy associated with
    the specified vault. The\n\t\t\toperation is eventually consistent&#8212;that
    is, it might take some time for Amazon Glacier to\n\t\t\tcompletely remove the
    access policy, and you might still see the effect of the policy\n\t\t\tfor a short
    time after you send the delete request. This operation is idempotent. You can
    invoke delete multiple times, even if there is\n\t\t\tno policy associated with
    the vault. For more information about vault access policies,\n\t\t\tsee Amazon
    Glacier Access Control with Vault Access Policies.RequestsTo delete the current
    vault access policy, send an HTTP DELETE request to\n\t\t\tthe URI of the vault's
    access-policy subresource."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{vaultName}/access-policy
  tags: Vault Access Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnameaccesspolicy-delete-openapi.md
- name: Amazon Glacier API Delete  Vault  Notifications
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation deletes the notification configuration set
    for a vault \n\t\t\tSet Vault Notification Configuration (PUT\n\t\tnotification-configuration).
    The operation is\n\t\t\teventually consistent&#8212;that is, it might take some
    time for Amazon Glacier to\n\t\t\tcompletely disable the notifications, and you
    might still receive some notifications for\n\t\t\ta short time after you send
    the delete request. RequestsTo delete a vault's notification configuration, send
    a DELETE request to the\n\t\t\tvault's notification-configuration subresource."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/notification-configuration
  tags: Vault Notifications
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamenotificationconfiguration-delete-openapi.md
- name: Amazon Glacier API Describe  Vault
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation returns information about a vault, including
    the vault Amazon Resource Name\n\t\t\t(ARN), the date the vault was created, the
    number of archives contained within the\n\t\t\tvault, and the total size of all
    the archives in the vault. The number of archives and\n\t\t\ttheir total size
    are as of the last vault inventory Amazon Glacier generated (see Working with
    Vaults in Amazon Glacier). Amazon Glacier\n\t\t\tgenerates vault inventories approximately
    daily. This means that if you add or remove an\n\t\t\tarchive from a vault, and
    then immediately send a Describe Vault request, the response\n\t\t\tmight not
    reflect the changes.  RequestsTo get information about a vault, send a GET request
    to the URI of the specific\n\t\t\tvault resource."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}
  tags: Vaults
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultname-get-openapi.md
- name: Amazon Glacier API Get  Vault  Access  Policy
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation retrieves the access-policy subresource
    set on the\n\t\t\tvault&#8212;for more information on setting this subresource,
    see Set Vault Access Policy (PUT access-policy). If\n\t\t\tthere is no access
    policy set on the vault, the operation returns a 404 Not\n\t\t\t\tfound error.
    For more information about vault access policies, see Amazon Glacier Access Control
    with Vault Access Policies.RequestsTo return the current vault access policy,
    send an HTTP GET request to\n\t\t\tthe URI of the vault's access-policy subresource."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{vaultName}/access-policy
  tags: Vault Access Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnameaccesspolicy-get-openapi.md
- name: Amazon Glacier API Get  Vault  Lock
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation retrieves the following attributes from
    the lock-policy\n\t\t\tsubresource set on the specified vault: \n\t\t\tThe vault
    lock policy set on the vault.The state of the vault lock, which is either InProgess
    or\n\t\t\t\t\t\t\tLocked.When the lock ID expires. The lock ID is used to complete
    the vault locking\n\t\t\t\t\t\tprocess.When the vault lock was initiated and put
    into the InProgress state.\n\t\tA vault lock is put into the InProgress state
    by calling Initiate Vault Lock (POST lock-policy). A vault\n\t\t\tlock is put
    into the Locked state by calling Complete Vault Lock (POST lockId). You can\n\t\t\tabort
    the vault locking process by calling Abort Vault Lock (DELETE lock-policy). For
    more information about the vault locking\n\t\t\tprocess, see Amazon Glacier Vault
    Lock.If there is no vault lock policy set on the vault, the operation returns
    a 404 Not\n\t\t\t\tfound error. For more information about vault lock policies,
    see Amazon Glacier Access Control with Vault Lock Policies.RequestsTo return the
    current vault lock policy and other attributes, send an HTTP GET\n\t\t\trequest
    to the URI of the vault's lock-policy subresource as shown in the\n\t\t\tfollowing
    syntax example."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{vaultName}/lock-policy
  tags: Vault Locks
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamelockpolicy-get-openapi.md
- name: Amazon Glacier API Get  Vault  Notifications
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation retrieves the notification-configuration
    subresource set on the\n\t\t\tvault (see Set Vault Notification Configuration
    (PUT\n\t\tnotification-configuration). If notification configuration for a\n\t\t\tvault
    is not set, the operation returns a 404 Not Found error. For more\n\t\t\tinformation
    about vault notifications, see Configuring Vault Notifications in Amazon Glacier.
    RequestsTo retrieve the notification configuration information, send a GET request
    to\n\t\t\tthe URI of a vault's notification-configuration subresource."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/notification-configuration
  tags: Vault Notifications
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamenotificationconfiguration-get-openapi.md
- name: Amazon Glacier API Initiate  Vault  Lock
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation initiates the vault locking process by doing
    the following: Installing a vault lock policy on the specified vault.Setting the
    lock state of vault lock to InProgress.Returning a lock ID, which is used to complete
    the vault locking process.\n\t\t\t\t\t\n\t\tYou can set one vault lock policy
    for each vault and this policy can be up to 20 KB in size.\n\t\t\tFor more information
    about vault lock policies, see Amazon Glacier Access Control with Vault Lock Policies.You
    must complete the vault locking process within 24 hours after the vault lock enters
    the\n\t\t\t\tInProgress state. After the 24 hour window ends, the lock ID expires,\n\t\t\tthe
    vault automatically exits the InProgress state, and the vault lock\n\t\t\tpolicy
    is removed from the vault. You call Complete Vault Lock (POST lockId) to complete
    the vault locking process by\n\t\t\tsetting the state of the vault lock to Locked.
    NoteAfter a vault lock is in the Locked state, you cannot initiate a new vault
    lock\n\t\t\t\tfor the vault.You can abort the vault locking process by calling
    Abort Vault Lock (DELETE lock-policy). You can get the state of the vault lock
    by\n\t\t\tcalling Get Vault Lock (GET lock-policy). For more\n\t\t\tinformation
    about the vault locking process, see Amazon Glacier Vault Lock.If this operation
    is called when the vault lock is in the InProgress state, the\n\t\t\toperation
    returns an AccessDeniedException error. When the vault lock is in\n\t\t\tthe InProgress
    state you must call Abort Vault Lock (DELETE lock-policy) before you can initiate
    a new vault lock\n\t\t\tpolicy. RequestsTo initiate the vault locking process,
    send an HTTP POST request to the URI of\n\t\t\tthe lock-policy subresource of
    the vault, as shown in the following syntax\n\t\t\texample."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{vaultName}/lock-policy
  tags: Vault Locks
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamelockpolicy-post-openapi.md
- name: Amazon Glacier API List  Vaults
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation lists all vaults owned by the calling user&#8217;s
    account. The list returned in\n\t\t\tthe response is ASCII-sorted by vault name.
    By default, this operation returns up to 1,000 items per request. If there are
    more vaults\n\t\t\tto list, the marker field in the response body contains the
    vault Amazon\n\t\t\tResource Name (ARN) at which to continue the list with a new
    List Vaults request;\n\t\t\totherwise, the marker field is null. In your next
    List Vaults\n\t\t\trequest you set the marker parameter to the value Amazon Glacier
    returned in the\n\t\t\tresponses to your previous List Vaults request. You can
    also limit the number of vaults\n\t\t\treturned in the response by specifying
    the limit parameter in the request. RequestsTo get a list of vaults, you send
    a GET request to the\n\t\t\t\tvaults resource."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults
  tags: Vaults
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaults-get-openapi.md
- name: Amazon Glacier API Set  Vault  Access  Policy
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation configures an access policy for a vault
    and will overwrite an existing\n\t\t\tpolicy. To configure a vault access policy,
    send a PUT request to the\n\t\t\t\taccess-policy subresource of the vault. You
    can set one access policy per vault\n\t\t\tand the policy can be up to 20 KB in
    size. For more information about vault access\n\t\t\tpolicies, see Amazon Glacier
    Access Control with Vault Access Policies. Requests"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{vaultName}/access-policy
  tags: Vault Access Policies
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnameaccesspolicy-put-openapi.md
- name: Amazon Glacier API Set  Vault  Notification  Configuration
  x-api-slug: amazon-glacier-api
  description: "DescriptionRetrieving an archive and a vault inventory are asynchronous
    operations in Amazon Glacier for which\n\t\t\tyou must first initiate a job and
    wait for the job to complete before you can download\n\t\t\tthe job output. Most
    Amazon Glacier jobs take about four hours to complete. You can configure a\n\t\t\tvault
    to post a message to an Amazon Simple Notification Service (Amazon SNS) topic
    when these jobs complete. You can\n\t\t\tuse this operation to set notification
    configuration on the vault. For more information,\n\t\t\tsee Configuring Vault
    Notifications in Amazon Glacier.\n\t\t\t\n\t\tTo configure vault notifications,
    send a PUT request to the\n\t\t\t\tnotification-configuration subresource of the
    vault. A notification\n\t\t\tconfiguration is specific to a vault; therefore,
    it is also referred to as a vault\n\t\t\tsubresource. The request should include
    a JSON document that provides an Amazon Simple Notification Service (Amazon SNS)
    topic and the events for which you want Amazon Glacier to\n\t\t\tsend notifications
    to the topic.You can configure a vault to publish a notification for the following
    vault events:\n\t\t\tArchiveRetrievalCompleted&#8212; This event\n\t\t\t\t\t\toccurs
    when a job that was initiated for an archive retrieval is completed\n\t\t\t\t\t\t\t(Initiate
    Job (POST jobs)). The status of the completed\n\t\t\t\t\t\tjob can be Succeeded
    or Failed. The notification\n\t\t\t\t\t\tsent to the SNS topic is the same output
    as returned from Describe Job (GET JobID).InventoryRetrievalCompleted&#8212; This
    event\n\t\t\t\t\t\toccurs when a job that was initiated for an inventory retrieval
    is completed\n\t\t\t\t\t\t\t(Initiate Job (POST jobs)). The status of the completed\n\t\t\t\t\t\tjob
    can be Succeeded or Failed. The notification\n\t\t\t\t\t\tsent to the SNS topic
    is the same output as returned from Describe Job (GET JobID).\n\t\tAmazon SNS
    topics must grant permission to the vault to be allowed to publish notifications\n\t\t\tto
    the topic.RequestsTo set notification configuration on your vault, send a PUT
    request to the URI of the\n\t\t\tvault's notification-configuration subresource.
    You specify the\n\t\t\tconfiguration in the request body. The configuration includes
    the Amazon SNS topic name\n\t\t\tand an array of events that trigger notification
    to each topic."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/notification-configuration
  tags: Vault Notifications
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamenotificationconfiguration-put-openapi.md
- name: Amazon Glacier API Delete  Archive
  x-api-slug: amazon-glacier-api
  description: "DescriptionThis operation deletes an archive from a vault. You can
    delete one archive at a time from a vault. \n\t\t\tTo delete the archive you must
    provide its archive ID in the delete request. \n\t\t\tYou can get the archive
    ID by downloading the vault inventory for the vault that contains the archive.
    \n\t\t\tFor more information about downloading the vault inventory, \n\t\t\tsee
    Downloading a Vault Inventory in Amazon Glacier.After you delete an archive, you
    might still\n\t\t\tbe able to make a successful request to initiate a job to retrieve
    the deleted archive,\n\t\t\tbut the archive retrieval job will fail. Archive retrievals
    that are in progress for an archive ID when you delete the\n\t\t\tarchive might
    or might not succeed according to the following scenarios:\n\t\t\tIf the archive
    retrieval job is actively preparing the data for download when Amazon Glacier\n\t\t\t\t\t\treceives
    the delete archive request, the archival retrieval\toperation might fail. If the
    archive retrieval job has successfully prepared the archive for download when\n\t\t\t\t\t\tAmazon
    Glacier receives the delete archive request, you will be able to\n\t\t\t\t\t\tdownload
    the output. \n\t\tFor more information about archive retrieval, see \n\t\t\tDownloading
    an Archive in Amazon Glacier. This operation is idempotent. Attempting\n\t\t\tto
    delete an already-deleted archive does not result in an error. RequestsTo delete
    an archive you send a DELETE request to the archive resource\n\t\t\tURI."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: ://///{AccountId}/vaults/{VaultName}/archives/{ArchiveID}
  tags: Archives
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/accountidvaultsvaultnamearchivesarchiveid-delete-openapi.md
- name: Amazon Glacier API List  Provisioned  Capacity
  x-api-slug: amazon-glacier-api
  description: "List Provisioned Capacity (GET\n        provisioned-capacity)This
    operation lists the provisioned capacity for the specified AWS account.\n        Request
    SyntaxTo list the provisioned retrieval capacity for an account, send an HTTP
    GET request\n            to the provisioned-capacity URI as shown in the following
    syntax example.GET /AccountId/provisioned-capacity HTTP/1.1\nHost: glacier.Region.amazonaws.com\nDate:
    Date\nAuthorization: SignatureValue\nx-amz-glacier-version: 2012-06-01\n\n              NoteThe
    AccountId value is the AWS account ID. This value must match the AWS account ID
    associated with the credentials used to sign the request. You can either specify
    an AWS account ID or optionally a single '-' (hyphen), in which case Amazon Glacier
    uses the AWS account ID associated with the credentials used to sign the request.
    If you specify your account ID, do not include any hyphens ('-') in the ID.\n
    \         Request ParametersThis operation does not use request parameters.Request
    HeadersThis operation uses only request headers that are common to all operations.
    For information about common request headers, see \n\tCommon Request Headers.Request
    BodyThis operation does not have a request body.ResponsesIf the operation is successful,
    the service sends back an HTTP 200 OK response."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: :////Synta
  tags: ~
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/synta-syntax-openapi.md
- name: Amazon Glacier API
  x-api-slug: amazon-glacier-api
  description: Amazon Glacier is a secure, durable, and extremely low-cost cloud storage
    service for data archiving and long-term backup. Customers can reliably store
    large or small amounts of data for as little as $0.004 per gigabyte per month,
    a significant savings compared to on-premises solutions. To keep costs low yet
    suitable for varying retrieval needs, Amazon Glacier provides three options for
    access to archives, from a few minutes to several hours.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Storage-Content-Delivery_AmazonGlacier.png
  humanURL: https://aws.amazon.com/glacier/
  baseURL: :///
  tags: AWS Glacier
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/aws-glacier/master/_listings/aws-glacier/openapi.md
x-common:
- type: x-change-log
  url: http://aws.amazon.com/releasenotes/Amazon-Glacier/
- type: x-documentation
  url: http://docs.aws.amazon.com/amazonglacier/latest/dev/amazon-glacier-api.html
- type: x-faq
  url: https://aws.amazon.com/glacier/faqs/
- type: x-forum
  url: https://forums.aws.amazon.com/forum.jspa?forumID=140
- type: x-getting-started
  url: https://aws.amazon.com/glacier/getting-started/
- type: x-pricing
  url: https://aws.amazon.com/glacier/pricing/
- type: x-website
  url: https://aws.amazon.com/glacier/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---