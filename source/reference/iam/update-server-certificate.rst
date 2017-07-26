[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-server-certificate:


*************************
update-server-certificate
*************************



===========
Description
===========



Updates the name and/or the path of the specified server certificate stored in IAM.

 

For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs.html>`_ in the *IAM User Guide* .

 

.. warning::

   

  You should understand the implications of changing a server certificate's path or name. For more information, see `Renaming a Server Certificate <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs_manage.html#RenamingServerCerts>`_ in the *IAM User Guide* .

   

 

.. note::

   

  To change a server certificate name the requester must have appropriate permissions on both the source object and the target object. For example, to change the name from "ProductionCert" to "ProdCert", the entity making the request must have permission on "ProductionCert" and "ProdCert", or must have permission on all (*). For more information about permissions, see `Access Management <http://docs.aws.amazon.com/IAM/latest/UserGuide/access.html>`_ in the *IAM User Guide* .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UpdateServerCertificate>`_


========
Synopsis
========

::

    update-server-certificate
  --server-certificate-name <value>
  [--new-path <value>]
  [--new-server-certificate-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--server-certificate-name`` (string)


  The name of the server certificate that you want to update.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--new-path`` (string)


  The new path for the server certificate. Include this only if you are updating the server certificate's path.

   

  This paramater allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

  

``--new-server-certificate-name`` (string)


  The new name for the server certificate. Include this only if you are updating the server certificate's name. The name of the certificate cannot contain any spaces.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None