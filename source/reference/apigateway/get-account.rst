[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-account:


***********
get-account
***********



===========
Description
===========



Gets information about the current  Account resource.



========
Synopsis
========

::

    get-account
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

cloudwatchRoleArn -> (string)

  

  Specifies the Amazon resource name (ARN) of an Amazon CloudWatch role for the current  Account resource.

  

  

throttleSettings -> (structure)

  

  Specifies the application programming interface (API) throttle settings for the current  Account resource.

  

  burstLimit -> (integer)

    

    Returns the burstLimit when **ThrottleSettings** is called.

    

    

  rateLimit -> (double)

    

    Returns the rateLimit when **ThrottleSettings** is called.

    

    

  

