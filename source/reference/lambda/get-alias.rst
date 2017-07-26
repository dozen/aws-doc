[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda get-alias:


*********
get-alias
*********



===========
Description
===========



Returns the specified alias information such as the alias ARN, description, and function version it is pointing to. For more information, see `Introduction to AWS Lambda Aliases`_ .

 

This requires permission for the ``lambda:GetAlias`` action.



========
Synopsis
========

::

    get-alias
  --function-name <value>
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--function-name`` (string)


  Function name for which the alias is created. An alias is a subresource that exists only in the context of an existing Lambda function so you must specify the function name.

  

``--name`` (string)


  Name of the alias for which you want to retrieve information.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

AliasArn -> (string)

  

  Lambda function ARN that is qualified using the alias name as the suffix. For example, if you create an alias called ``BETA`` that points to a helloworld function version, the ARN is ``arn:aws:lambda:aws-regions:acct-id:function:helloworld:BETA`` .

  

  

Name -> (string)

  

  name name.

  

  

FunctionVersion -> (string)

  

  Function version to which the alias points.

  

  

Description -> (string)

  

  name description.

  

  



.. _Introduction to AWS Lambda Aliases: http://docs.aws.amazon.com/lambda/latest/dg/aliases-intro.html
