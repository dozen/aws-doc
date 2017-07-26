[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-signing-certificates:


*************************
list-signing-certificates
*************************



===========
Description
===========



Returns information about the signing certificates associated with the specified user. If there are none, the action returns an empty list. 

 

Although each user is limited to a small number of signing certificates, you can still paginate the results using the ``MaxItems`` and ``Marker`` parameters. 

 

If the ``UserName`` field is not specified, the user name is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users. 



``list-signing-certificates`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Certificates``


========
Synopsis
========

::

    list-signing-certificates
  [--user-name <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user.

  

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



========
Examples
========

**To list the signing certificates for an IAM user**

The following ``list-signing-certificates`` command lists the signing certificates for the IAM user named ``Bob``::

  aws iam list-signing-certificates --user-name Bob

Output::

  {
    "Certificates: "[
      {
        "UserName": "Bob",
        "Status": "Inactive",
        "CertificateBody": "-----BEGIN CERTIFICATE-----<certificate-body>-----END CERTIFICATE-----",
        "CertificateId": "TA7SMP42TDN5Z26OBPJE7EXAMPLE",
        "UploadDate": "2013-06-06T21:40:08Z"
      }
    ]
  }

For more information, see `Creating and Uploading a User Signing Certificate`_ in the *Using IAM* guide.

.. _`Creating and Uploading a User Signing Certificate`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_UploadCertificate.html



======
Output
======

Certificates -> (list)

  

  A list of the user's signing certificate information.

  

  (structure)

    

    Contains information about an X.509 signing certificate.

     

    This data type is used as a response element in the  upload-signing-certificate and  list-signing-certificates actions. 

    

    UserName -> (string)

      

      The name of the user the signing certificate is associated with.

      

      

    CertificateId -> (string)

      

      The ID for the signing certificate.

      

      

    CertificateBody -> (string)

      

      The contents of the signing certificate.

      

      

    Status -> (string)

      

      The status of the signing certificate. ``Active`` means the key is valid for API calls, while ``Inactive`` means it is not.

      

      

    UploadDate -> (timestamp)

      

      The date when the signing certificate was uploaded.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  

