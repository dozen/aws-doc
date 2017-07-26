[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda update-alias:


************
update-alias
************



===========
Description
===========



Using this API you can update the function version to which the alias points and the alias description. For more information, see `Introduction to AWS Lambda Aliases`_ .

 

This requires permission for the lambda:UpdateAlias action.



========
Synopsis
========

::

    update-alias
  --function-name <value>
  --name <value>
  [--function-version <value>]
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--function-name`` (string)


  The function name for which the alias is created.

  

``--name`` (string)


  The alias name.

  

``--function-version`` (string)


  Using this parameter you can change the Lambda function version to which the alias points.

  

``--description`` (string)


  You can change the description of the alias using this parameter.

  

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
