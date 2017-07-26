[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront create-cloud-front-origin-access-identity:


*****************************************
create-cloud-front-origin-access-identity
*****************************************



===========
Description
===========



Creates a new origin access identity. If you're using Amazon S3 for your origin, you can use an origin access identity to require users to access your content using a CloudFront URL instead of the Amazon S3 URL. For more information about how to use origin access identities, see `Serving Private Content through CloudFront <http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/PrivateContent.html>`_ in the *Amazon CloudFront Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/CreateCloudFrontOriginAccessIdentity>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    create-cloud-front-origin-access-identity
  --cloud-front-origin-access-identity-config <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cloud-front-origin-access-identity-config`` (structure)


  The current configuration information for the identity.

  



Shorthand Syntax::

    CallerReference=string,Comment=string




JSON Syntax::

  {
    "CallerReference": "string",
    "Comment": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CloudFrontOriginAccessIdentity -> (structure)

  

  The origin access identity's information.

  

  Id -> (string)

    

    The ID for the origin access identity. For example: ``E74FTE3AJFJ256A`` . 

    

    

  S3CanonicalUserId -> (string)

    

    The Amazon S3 canonical user ID for the origin access identity, used when giving the origin access identity read permission to an object in Amazon S3. 

    

    

  CloudFrontOriginAccessIdentityConfig -> (structure)

    

    The current configuration information for the identity. 

    

    CallerReference -> (string)

      

      A unique number that ensures the request can't be replayed.

       

      If the ``CallerReference`` is new (no matter the content of the ``cloud-front-origin-access-identity-config`` object), a new origin access identity is created.

       

      If the ``CallerReference`` is a value already sent in a previous identity request, and the content of the ``cloud-front-origin-access-identity-config`` is identical to the original request (ignoring white space), the response includes the same information returned to the original request. 

       

      If the ``CallerReference`` is a value you already sent in a previous request to create an identity, but the content of the ``cloud-front-origin-access-identity-config`` is different from the original request, CloudFront returns a ``CloudFrontOriginAccessIdentityAlreadyExists`` error. 

      

      

    Comment -> (string)

      

      Any comments you want to include about the origin access identity. 

      

      

    

  

Location -> (string)

  

  The fully qualified URI of the new origin access identity just created. For example: ``https://cloudfront.amazonaws.com/2010-11-01/origin-access-identity/cloudfront/E74FTE3AJFJ256A`` .

  

  

ETag -> (string)

  

  The current version of the origin access identity created.

  

  

