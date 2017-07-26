[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-account:


**************
update-account
**************



===========
Description
===========



Changes information about the current  Account resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/UpdateAccount>`_


========
Synopsis
========

::

    update-account
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--patch-operations`` (list)


  A list of update operations to be applied to the specified resource and in the order specified in this list.

  



Shorthand Syntax::

    op=string,path=string,value=string,from=string ...




JSON Syntax::

  [
    {
      "op": "add"|"remove"|"replace"|"move"|"copy"|"test",
      "path": "string",
      "value": "string",
      "from": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change the IAM Role ARN for logging to CloudWatch Logs**

Command::

  aws apigateway update-account --patch-operations op='replace',path='/cloudwatchRoleArn',value='arn:aws:iam::123412341234:role/APIGatewayToCloudWatchLogs'

Output::

  {
      "cloudwatchRoleArn": "arn:aws:iam::123412341234:role/APIGatewayToCloudWatchLogs", 
      "throttleSettings": {
          "rateLimit": 1000.0, 
          "burstLimit": 2000
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

  

  

