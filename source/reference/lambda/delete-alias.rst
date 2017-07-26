[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda delete-alias:


************
delete-alias
************



===========
Description
===========



Deletes the specified Lambda function alias. For more information, see `Introduction to AWS Lambda Aliases`_ .

 

This requires permission for the lambda:DeleteAlias action.



========
Synopsis
========

::

    delete-alias
  --function-name <value>
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--function-name`` (string)


  The Lambda function name for which the alias is created. Deleting an alias does not delete the function version to which it is pointing. 

  

``--name`` (string)


  Name of the alias to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Introduction to AWS Lambda Aliases: http://docs.aws.amazon.com/lambda/latest/dg/aliases-intro.html
