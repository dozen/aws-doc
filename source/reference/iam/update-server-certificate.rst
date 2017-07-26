[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-server-certificate:


*************************
update-server-certificate
*************************



===========
Description
===========



Updates the name and/or the path of the specified server certificate.

 

For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .

 

.. warning::

  You should understand the implications of changing a server certificate's path or name. For more information, see `Renaming a Server Certificate`_ in the *IAM User Guide* .

 

.. note::

  To change a server certificate name the requester must have appropriate permissions on both the source object and the target object. For example, to change the name from ProductionCert to ProdCert, the entity making the request must have permission on ProductionCert and ProdCert, or must have permission on all (*). For more information about permissions, see `Access Management`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    update-server-certificate
  --server-certificate-name <value>
  [--new-path <value>]
  [--new-server-certificate-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--server-certificate-name`` (string)


  The name of the server certificate that you want to update.

  

``--new-path`` (string)


  The new path for the server certificate. Include this only if you are updating the server certificate's path. 

  

``--new-server-certificate-name`` (string)


  The new name for the server certificate. Include this only if you are updating the server certificate's name. The name of the certificate cannot contain any spaces.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Working with Server Certificates: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs.html
.. _Renaming a Server Certificate: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs_manage.html#RenamingServerCerts
.. _Access Management: http://docs.aws.amazon.com/IAM/latest/UserGuide/access.html
