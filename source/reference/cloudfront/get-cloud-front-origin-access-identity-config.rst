[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront get-cloud-front-origin-access-identity-config:


*********************************************
get-cloud-front-origin-access-identity-config
*********************************************



===========
Description
===========



Get the configuration information about an origin access identity. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/GetCloudFrontOriginAccessIdentityConfig>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    get-cloud-front-origin-access-identity-config
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The identity's ID. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON id provided. The JSON id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CloudFrontOriginAccessIdentityConfig -> (structure)

  

  The origin access identity's configuration information. 

  

  CallerReference -> (string)

    

    A unique number that ensures the request can't be replayed.

     

    If the ``CallerReference`` is new (no matter the content of the ``CloudFrontOriginAccessIdentityConfig`` object), a new origin access identity is created.

     

    If the ``CallerReference`` is a value already sent in a previous identity request, and the content of the ``CloudFrontOriginAccessIdentityConfig`` is identical to the original request (ignoring white space), the response includes the same information returned to the original request. 

     

    If the ``CallerReference`` is a value you already sent in a previous request to create an identity, but the content of the ``CloudFrontOriginAccessIdentityConfig`` is different from the original request, CloudFront returns a ``CloudFrontOriginAccessIdentityAlreadyExists`` error. 

    

    

  Comment -> (string)

    

    Any comments you want to include about the origin access identity. 

    

    

  

ETag -> (string)

  

  The current version of the configuration. For example: ``E2QWRUHAPOMQZL`` .

  

  

