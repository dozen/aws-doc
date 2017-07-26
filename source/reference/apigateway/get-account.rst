[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-account:


***********
get-account
***********



===========
Description
===========



Gets information about the current  Account resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetAccount>`_


========
Synopsis
========

::

    get-account
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get API Gateway account settings**

Command::

  aws apigateway get-account

Output::

  {
      "cloudwatchRoleArn": "arn:aws:iam::123412341234:role/APIGatewayToCloudWatchLogsRole", 
      "throttleSettings": {
          "rateLimit": 500.0, 
          "burstLimit": 1000
      }
  }


======
Output
======

cloudwatchRoleArn -> (string)

  

  The ARN of an Amazon CloudWatch role for the current  Account . 

  

  

throttleSettings -> (structure)

  

  Specifies the API request limits configured for the current  Account .

  

  burstLimit -> (integer)

    

    The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.

    

    

  rateLimit -> (double)

    

    The API request steady-state rate limit.

    

    

  

features -> (list)

  

  A list of features supported for the account. When usage plans are enabled, the features list will include an entry of ``"UsagePlans"`` .

  

  (string)

    

    

  

apiKeyVersion -> (string)

  

  The version of the API keys used for the account.

  

  

