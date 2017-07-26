[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda delete-alias:


************
delete-alias
************



===========
Description
===========



Deletes the specified Lambda function alias. For more information, see `Introduction to AWS Lambda Aliases <http://docs.aws.amazon.com/lambda/latest/dg/aliases-intro.html>`_ .

 

This requires permission for the lambda:DeleteAlias action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/DeleteAlias>`_


========
Synopsis
========

::

    delete-alias
  --function-name <value>
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--function-name`` (string)


  The Lambda function name for which the alias is created. Deleting an alias does not delete the function version to which it is pointing. Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 characters in length.

  

``--name`` (string)


  Name of the alias to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None