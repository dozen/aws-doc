[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp describe-user-pool-domain:


*************************
describe-user-pool-domain
*************************



===========
Description
===========



Gets information about a domain.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/DescribeUserPoolDomain>`_


========
Synopsis
========

::

    describe-user-pool-domain
  --domain <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain`` (string)


  The domain string.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DomainDescription -> (structure)

  

  A domain description object containing information about the domain.

  

  UserPoolId -> (string)

    

    The user pool ID.

    

    

  AWSAccountId -> (string)

    

    The AWS account ID for the user pool owner.

    

    

  Domain -> (string)

    

    The domain string.

    

    

  S3Bucket -> (string)

    

    The S3 bucket where the static files for this domain are stored.

    

    

  CloudFrontDistribution -> (string)

    

    The ARN of the CloudFront distribution.

    

    

  Version -> (string)

    

    The app version.

    

    

  Status -> (string)

    

    The domain status.

    

    

  

