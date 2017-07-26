[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-applications:


*****************
list-applications
*****************



===========
Description
===========



Lists the ARNs of the applications within this AWS account. For more information about applications, see `Inspector Applications`_ .



========
Synopsis
========

::

    list-applications
  [--filter <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--filter`` (structure)


  You can use this parameter to specify a subset of data to be included in the action's response.

   

  For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

  



Shorthand Syntax::

    applicationNamePatterns=string,string




JSON Syntax::

  {
    "applicationNamePatterns": ["string", ...]
  }



``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to 'null' on your first call to the **list-applications** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

applicationArnList -> (list)

  

  A list of ARNs specifying the applications returned by the action.

  

  (string)

    

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to 'null'.

  

  



.. _Inspector Applications: https://docs.aws.amazon.com/inspector/latest/userguide//inspector_applications.html
