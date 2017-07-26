[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda update-alias:


************
update-alias
************



===========
Description
===========



Using this API you can update the function version to which the alias points and the alias description. For more information, see `Introduction to AWS Lambda Aliases <http://docs.aws.amazon.com/lambda/latest/dg/aliases-intro.html>`_ .

 

This requires permission for the lambda:UpdateAlias action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/UpdateAlias>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--function-name`` (string)


  The function name for which the alias is created. Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 characters in length.

  

``--name`` (string)


  The alias name.

  

``--function-version`` (string)


  Using this parameter you can change the Lambda function version to which the alias points.

  

``--description`` (string)


  You can change the description of the alias using this parameter.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

