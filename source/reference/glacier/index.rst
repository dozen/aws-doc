[ :ref:`aws <cli:aws>` ]

.. _cli:aws glacier:


*******
glacier
*******



===========
Description
===========



Amazon Glacier is a storage solution for "cold data."

 

Amazon Glacier is an extremely low-cost storage service that provides secure, durable, and easy-to-use storage for data backup and archival. With Amazon Glacier, customers can store their data cost effectively for months, years, or decades. Amazon Glacier also enables customers to offload the administrative burdens of operating and scaling storage to AWS, so they don't have to worry about capacity planning, hardware provisioning, data replication, hardware failure and recovery, or time-consuming hardware migrations.

 

Amazon Glacier is a great storage choice when low storage cost is paramount, your data is rarely retrieved, and retrieval latency of several hours is acceptable. If your application requires fast or frequent access to your data, consider using Amazon S3. For more information, go to `Amazon Simple Storage Service (Amazon S3)`_ .

 

You can store any kind of data in any format. There is no maximum limit on the total amount of data you can store in Amazon Glacier. 

 

If you are a first-time user of Amazon Glacier, we recommend that you begin by reading the following sections in the *Amazon Glacier Developer Guide* :

 

 
* `What is Amazon Glacier`_ - This section of the Developer Guide describes the underlying data model, the operations it supports, and the AWS SDKs that you can use to interact with the service.
 
* `Getting Started with Amazon Glacier`_ - The Getting Started section walks you through the process of creating a vault, uploading archives, creating jobs to download archives, retrieving the job output, and deleting archives.
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  abort-multipart-upload
  abort-vault-lock
  add-tags-to-vault
  complete-multipart-upload
  complete-vault-lock
  create-vault
  delete-archive
  delete-vault
  delete-vault-access-policy
  delete-vault-notifications
  describe-job
  describe-vault
  get-data-retrieval-policy
  get-job-output
  get-vault-access-policy
  get-vault-lock
  get-vault-notifications
  initiate-job
  initiate-multipart-upload
  initiate-vault-lock
  list-jobs
  list-multipart-uploads
  list-parts
  list-tags-for-vault
  list-vaults
  remove-tags-from-vault
  set-data-retrieval-policy
  set-vault-access-policy
  set-vault-notifications
  upload-archive
  upload-multipart-part


.. _What is Amazon Glacier: http://docs.aws.amazon.com/amazonglacier/latest/dev/introduction.html
.. _Amazon Simple Storage Service (Amazon S3): http://aws.amazon.com/s3/
.. _Getting Started with Amazon Glacier: http://docs.aws.amazon.com/amazonglacier/latest/dev/amazon-glacier-getting-started.html
