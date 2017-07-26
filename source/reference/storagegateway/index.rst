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

 

 
* `AWS Storage Gateway Required Request Headers`_ : Describes the required headers that you must send with every POST request to AWS Storage Gateway.
 
* `Signing Requests`_ : AWS Storage Gateway requires that you authenticate every request you send; this topic describes how sign such a request.
 
* `Error Responses`_ : Provides reference information about AWS Storage Gateway errors.
 
* `Operations in AWS Storage Gateway`_ : Contains detailed descriptions of all AWS Storage Gateway operations, their request parameters, response elements, possible errors, and examples of requests and responses.
 
* `AWS Storage Gateway Regions and Endpoints`_ : Provides a list of each of the regions and endpoints available for use with AWS Storage Gateway. 
 

 

.. note::

  AWS Storage Gateway resource IDs are in uppercase. When you use these resource IDs with the Amazon EC2 API, EC2 expects resource IDs in lowercase. You must change your resource ID to lowercase to use it with the EC2 API. For example, in Storage Gateway the ID for a volume might be vol-1122AABB. When you use this ID with the EC2 API, you must change it to vol-1122aabb. Otherwise, the EC2 API might not behave as expected.



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
  create-snapshot
  create-snapshot-from-volume-recovery-point
  create-stored-iscsi-volume
  create-tape-with-barcode
  create-tapes
  delete-bandwidth-rate-limit
  delete-chap-credentials
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
  describe-snapshot-schedule
  describe-stored-iscsi-volumes
  describe-tape-archives
  describe-tape-recovery-points
  describe-tapes
  describe-upload-buffer
  describe-vtl-devices
  describe-working-storage
  disable-gateway
  list-gateways
  list-local-disks
  list-tags-for-resource
  list-volume-initiators
  list-volume-recovery-points
  list-volumes
  remove-tags-from-resource
  reset-cache
  retrieve-tape-archive
  retrieve-tape-recovery-point
  shutdown-gateway
  start-gateway
  update-bandwidth-rate-limit
  update-chap-credentials
  update-gateway-information
  update-gateway-software-now
  update-maintenance-start-time
  update-snapshot-schedule
  update-vtl-device-type


.. _AWS Storage Gateway Required Request Headers: http://docs.aws.amazon.com/storagegateway/latest/userguide/AWSStorageGatewayHTTPRequestsHeaders.html
.. _Signing Requests: http://docs.aws.amazon.com/storagegateway/latest/userguide/AWSStorageGatewaySigningRequests.html
.. _Operations in AWS Storage Gateway: http://docs.aws.amazon.com/storagegateway/latest/userguide/AWSStorageGatewayAPIOperations.html
.. _AWS Storage Gateway Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/index.html?rande.html
.. _Error Responses: http://docs.aws.amazon.com/storagegateway/latest/userguide/APIErrorResponses.html
