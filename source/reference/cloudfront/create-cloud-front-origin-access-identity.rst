[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront create-cloud-front-origin-access-identity:


*****************************************
create-cloud-front-origin-access-identity
*****************************************



===========
Description
===========

Create a new origin access identity.

.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    create-cloud-front-origin-access-identity
  --cloud-front-origin-access-identity-config <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cloud-front-origin-access-identity-config`` (structure)
The origin access identity's configuration information.



Shorthand Syntax::

    CallerReference=string,Comment=string




JSON Syntax::

  {
    "CallerReference": "string",
    "Comment": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

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

      A unique number that ensures the request can't be replayed. If the CallerReference is new (no matter the content of the cloud-front-origin-access-identity-config object), a new origin access identity is created. If the CallerReference is a value you already sent in a previous request to create an identity, and the content of the cloud-front-origin-access-identity-config is identical to the original request (ignoring white space), the response includes the same information returned to the original request. If the CallerReference is a value you already sent in a previous request to create an identity but the content of the cloud-front-origin-access-identity-config is different from the original request, CloudFront returns a CloudFrontOriginAccessIdentityAlreadyExists error.

      

    Comment -> (string)

      Any comments you want to include about the origin access identity.

      

    

  

Location -> (string)

  The fully qualified URI of the new origin access identity just created. For example: https://cloudfront.amazonaws.com/2010-11-01/origin-access-identity/cloudfront/E74FTE3AJFJ256A.

  

ETag -> (string)

  The current version of the origin access identity created.

  

