[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-server-certificates:


************************
list-server-certificates
************************



===========
Description
===========



Lists the server certificates that have the specified path prefix. If none exist, the action returns an empty list. 

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 

 

For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .



``list-server-certificates`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ServerCertificateMetadataList``


========
Synopsis
========

::

    list-server-certificates
  [--path-prefix <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--path-prefix`` (string)


  The path prefix for filtering the results. For example: ``/company/servercerts`` would get all server certificates for which the path starts with ``/company/servercerts`` . 

   

  This parameter is optional. If it is not included, it defaults to a slash (/), listing all server certificates. 

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ServerCertificateMetadataList -> (list)

  

  A list of server certificates.

  

  (structure)

    

    Contains information about a server certificate without its certificate body, certificate chain, and private key. 

     

    This data type is used as a response element in the  upload-server-certificate and  list-server-certificates actions. 

    

    Path -> (string)

      

      The path to the server certificate. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    ServerCertificateName -> (string)

      

      The name that identifies the server certificate.

      

      

    ServerCertificateId -> (string)

      

      The stable and unique string identifying the server certificate. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) specifying the server certificate. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    UploadDate -> (timestamp)

      

      The date when the server certificate was uploaded.

      

      

    Expiration -> (timestamp)

      

      The date on which the certificate is set to expire.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _Working with Server Certificates: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
