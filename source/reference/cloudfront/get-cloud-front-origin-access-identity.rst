[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront get-cloud-front-origin-access-identity:


**************************************
get-cloud-front-origin-access-identity
**************************************



===========
Description
===========

Get the information about an origin access identity.

.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    get-cloud-front-origin-access-identity
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)
The identity's id.

``--cli-input-json`` (string)
Performs service operation based on the JSON id provided. The JSON id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

CloudFrontOriginAccessIdentity -> (structure)

  The origin access identity's information.

  Id -> (string)

    The ID for the origin access identity. For example: E74FTE3AJFJ256A.

    

  S3CanonicalUserId -> (string)

    The Amazon S3 canonical user ID for the origin access identity, which you use when giving the origin access identity read permission to an object in Amazon S3.

    

  CloudFrontOriginAccessIdentityConfig -> (structure)

    The current configuration information for the identity.

    CallerReference -> (string)

      A unique number that ensures the request can't be replayed. If the CallerReference is new (no matter the content of the CloudFrontOriginAccessIdentityConfig object), a new origin access identity is created. If the CallerReference is a value you already sent in a previous request to create an identity, and the content of the CloudFrontOriginAccessIdentityConfig is identical to the original request (ignoring white space), the response includes the same information returned to the original request. If the CallerReference is a value you already sent in a previous request to create an identity but the content of the CloudFrontOriginAccessIdentityConfig is different from the original request, CloudFront returns a CloudFrontOriginAccessIdentityAlreadyExists error.

      

    Comment -> (string)

      Any comments you want to include about the origin access identity.

      

    

  

ETag -> (string)

  The current version of the origin access identity's information. For example: E2QWRUHAPOMQZL.

  
