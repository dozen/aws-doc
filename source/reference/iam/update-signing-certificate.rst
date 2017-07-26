[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-signing-certificate:


**************************
update-signing-certificate
**************************



===========
Description
===========



Changes the status of the specified user signing certificate from active to disabled, or vice versa. This action can be used to disable an IAM user's signing certificate as part of a certificate rotation work flow.

 

If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UpdateSigningCertificate>`_


========
Synopsis
========

::

    update-signing-certificate
  [--user-name <value>]
  --certificate-id <value>
  --status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the IAM user the signing certificate belongs to.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--certificate-id`` (string)


  The ID of the signing certificate you want to update.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters that can consist of any upper or lowercased letter or digit.

  

``--status`` (string)


  The status you want to assign to the certificate. ``Active`` means the certificate can be used for API calls to AWS, while ``Inactive`` means the certificate cannot be used.

  

  Possible values:

  
  *   ``Active``

  
  *   ``Inactive``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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