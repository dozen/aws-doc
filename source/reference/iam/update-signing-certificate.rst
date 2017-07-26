[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-signing-certificate:


**************************
update-signing-certificate
**************************



===========
Description
===========



Changes the status of the specified signing certificate from active to disabled, or vice versa. This action can be used to disable a user's signing certificate as part of a certificate rotation work flow. 

 

If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users. 



========
Synopsis
========

::

    update-signing-certificate
  [--user-name <value>]
  --certificate-id <value>
  --status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user the signing certificate belongs to.

  

``--certificate-id`` (string)


  The ID of the signing certificate you want to update.

  

``--status`` (string)


  The status you want to assign to the certificate. ``Active`` means the certificate can be used for API calls to AWS, while ``Inactive`` means the certificate cannot be used. 

  

  Possible values:

  
  *   ``Active``

  
  *   ``Inactive``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To activate or deactivate a signing certificate for an IAM user**

The following ``update-signing-certificate`` command deactivates the specified signing certificate for the IAM user named ``Bob``::

  aws iam update-signing-certificate --certificate-id TA7SMP42TDN5Z26OBPJE7EXAMPLE --status Inactive --user-name Bob

To get the ID for a signing certificate, use the ``list-signing-certificates`` command.

For more information, see `Creating and Uploading a User Signing Certificate`_ in the *Using IAM* guide.

.. _`Creating and Uploading a User Signing Certificate`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_UploadCertificate.html



======
Output
======

None