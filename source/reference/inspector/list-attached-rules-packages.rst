[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-attached-rules-packages:


****************************
list-attached-rules-packages
****************************



===========
Description
===========



Lists the rules packages attached to the assessment specified by the assessment ARN.



========
Synopsis
========

::

    list-attached-rules-packages
  --assessment-arn <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assessment-arn`` (string)


  The ARN specifying the assessment whose rules packages you want to list.

  

``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to 'null' on your first call to the **list-attached-rules-packages** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

rulesPackageArnList -> (list)

  

  A list of ARNs specifying the rules packages returned by the action.

  

  (string)

    

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to 'null'.

  

  

