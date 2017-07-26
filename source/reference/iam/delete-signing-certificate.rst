[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-signing-certificate:


**************************
delete-signing-certificate
**************************



===========
Description
===========



Deletes the specified signing certificate associated with the specified user.

 

If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users. 



========
Synopsis
========

::

    delete-signing-certificate
  [--user-name <value>]
  --certificate-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user the signing certificate belongs to.

  

``--certificate-id`` (string)


  The ID of the signing certificate to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a signing certificate for an IAM user**

The following ``delete-signing-certificate`` command deletes the specified signing certificate for the IAM user named ``Bob``::

  aws iam delete-signing-certificate --user-name Bob --certificate-id TA7SMP42TDN5Z26OBPJE7EXAMPLE

To get the ID for a signing certificate, use the ``list-signing-certificates`` command.

For more information, see `Creating and Uploading a User Signing Certificate`_ in the *Using IAM* guide.

.. _`Creating and Uploading a User Signing Certificate`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_UploadCertificate.html



======
Output
======

None