[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-signing-certificate:


**************************
delete-signing-certificate
**************************



===========
Description
===========



Deletes a signing certificate associated with the specified IAM user.

 

If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated IAM users.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/DeleteSigningCertificate>`_


========
Synopsis
========

::

    delete-signing-certificate
  [--user-name <value>]
  --certificate-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the user the signing certificate belongs to.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--certificate-id`` (string)


  The ID of the signing certificate to delete.

   

  The format of this parameter, as described by its `regex <http://wikipedia.org/wiki/regex>`_ pattern, is a string of characters that can be upper- or lower-cased letters or digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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