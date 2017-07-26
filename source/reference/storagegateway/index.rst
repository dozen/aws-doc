[ :ref:`aws <cli:aws>` ]

.. _cli:aws storagegateway:


**************
storagegateway
**************



===========
Description
===========

 

AWS Storage Gateway is the service that connects an on-premises software appliance with cloud-based storage to provide seamless and secure integration between an organization's on-premises IT environment and AWS's storage infrastructure. The service enables you to securely upload data to the AWS cloud for cost effective backup and rapid disaster recovery.

 

Use the following links to get started using the *AWS Storage Gateway Service API Reference* :

 

 
* `AWS Storage Gateway Required Request Headers <http://docs.aws.amazon.com/storagegateway/latest/userguide/AWSStorageGatewayAPI.html#AWSStorageGatewayHTTPRequestsHeaders>`_ : Describes the required headers that you must send with every POST request to AWS Storage Gateway. 
 
* `Signing Requests <http://docs.aws.amazon.com/storagegateway/latest/userguide/AWSStorageGatewayAPI.html#AWSStorageGatewaySigningRequests>`_ : AWS Storage Gateway requires that you authenticate every request you send; this topic describes how sign such a request. 
 
* `Error Responses <http://docs.aws.amazon.com/storagegateway/latest/userguide/AWSStorageGatewayAPI.html#APIErrorResponses>`_ : Provides reference information about AWS Storage Gateway errors. 
 
* `Operations in AWS Storage Gateway <http://docs.aws.amazon.com/storagegateway/latest/APIReference/API_Operations.html>`_ : Contains detailed descriptions of all AWS Storage Gateway operations, their request parameters, response elements, possible errors, and examples of requests and responses. 
 
* `AWS Storage Gateway Regions and Endpoints <http://docs.aws.amazon.com/general/latest/general/latest/gr/rande.html#sg_region>`_ : Provides a list of each region and endpoints available for use with AWS Storage Gateway. 
 

 

.. note::

   

  AWS Storage Gateway resource IDs are in uppercase. When you use these resource IDs with the Amazon EC2 API, EC2 expects resource IDs in lowercase. You must change your resource ID to lowercase to use it with the EC2 API. For example, in Storage Gateway the ID for a volume might be ``vol-AA22BB012345DAF670`` . When you use this ID with the EC2 API, you must change it to ``vol-aa22bb012345daf670`` . Otherwise, the EC2 API might not behave as expected.

   

 

.. warning::

   

  IDs for Storage Gateway volumes and Amazon EBS snapshots created from gateway volumes are changing to a longer format. Starting in December 2016, all new volumes and snapshots will be created with a 17-character string. Starting in April 2016, you will be able to use these longer IDs so you can test your systems with the new format. For more information, see `Longer EC2 and EBS Resource IDs <https://aws.amazon.com/ec2/faqs/#longer-ids>`_ .

   

  For example, a volume Amazon Resource Name (ARN) with the longer volume ID format looks like the following:

   

   ``arn:aws:storagegateway:us-west-2:111122223333:gateway/sgw-12A3456B/volume/vol-1122AABBCCDDEEFFG`` .

   

  A snapshot ID with the longer ID format looks like the following: ``snap-78e226633445566ee`` .

   

  For more information, see `Announcement\: Heads-up – Longer AWS Storage Gateway volume and snapshot IDs coming in 2016 <https://forums.aws.amazon.com/ann.jspa?annID=3557>`_ .

   



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  activate-gateway
  add-cache
  add-tags-to-resource
  add-upload-buffer
  add-working-storage
  cancel-archival
  cancel-retrieval
  create-cached-iscsi-volume
  create-nfs-file-share
  create-snapshot
  create-snapshot-from-volume-recovery-point
  create-stored-iscsi-volume
  create-tape-with-barcode
  create-tapes
  delete-bandwidth-rate-limit
  delete-chap-credentials
  delete-file-share
  delete-gateway
  delete-snapshot-schedule
  delete-tape
  delete-tape-archive
  delete-volume
  describe-bandwidth-rate-limit
  describe-cache
  describe-cached-iscsi-volumes
  describe-chap-credentials
  describe-gateway-information
  describe-maintenance-start-time
  describe-nfs-file-shares
  describe-snapshot-schedule
  describe-stored-iscsi-volumes
  describe-tape-archives
  describe-tape-recovery-points
  describe-tapes
  describe-upload-buffer
  describe-vtl-devices
  describe-working-storage
  disable-gateway
  list-file-shares
  list-gateways
  list-local-disks
  list-tags-for-resource
  list-tapes
  list-volume-initiators
  list-volume-recovery-points
  list-volumes
  refresh-cache
  remove-tags-from-resource
  reset-cache
  retrieve-tape-archive
  retrieve-tape-recovery-point
  set-local-console-password
  shutdown-gateway
  start-gateway
  update-bandwidth-rate-limit
  update-chap-credentials
  update-gateway-information
  update-gateway-software-now
  update-maintenance-start-time
  update-nfs-file-share
  update-snapshot-schedule
  update-vtl-device-type
