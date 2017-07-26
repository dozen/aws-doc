[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-server-certificates:


************************
list-server-certificates
************************



===========
Description
===========



Lists the server certificates stored in IAM that have the specified path prefix. If none exist, the action returns an empty list.

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.

 

For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/ListServerCertificates>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--path-prefix`` (string)


  The path prefix for filtering the results. For example: ``/company/servercerts`` would get all server certificates for which the path starts with ``/company/servercerts`` .

   

  This parameter is optional. If it is not included, it defaults to a slash (/), listing all server certificates. This paramater allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

  

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ServerCertificateMetadataList -> (list)

  

  A list of server certificates.

  

  (structure)

    

    Contains information about a server certificate without its certificate body, certificate chain, and private key.

     

    This data type is used as a response element in the  upload-server-certificate and  list-server-certificates actions. 

    

    Path -> (string)

      

      The path to the server certificate. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

      

      

    ServerCertificateName -> (string)

      

      The name that identifies the server certificate.

      

      

    ServerCertificateId -> (string)

      

      The stable and unique string identifying the server certificate. For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) specifying the server certificate. For more information about ARNs and how to use them in policies, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

      

      

    UploadDate -> (timestamp)

      

      The date when the server certificate was uploaded.

      

      

    Expiration -> (timestamp)

      

      The date on which the certificate is set to expire.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  

