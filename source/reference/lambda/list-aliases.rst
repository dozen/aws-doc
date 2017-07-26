[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda list-aliases:


************
list-aliases
************



===========
Description
===========



Returns list of aliases created for a Lambda function. For each alias, the response includes information such as the alias ARN, description, alias name, and the function version to which it points. For more information, see `Introduction to AWS Lambda Aliases`_ .

 

This requires permission for the lambda:ListAliases action.



========
Synopsis
========

::

    list-aliases
  --function-name <value>
  [--function-version <value>]
  [--marker <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--function-name`` (string)


  Lambda function name for which the alias is created.

  

``--function-version`` (string)


  If you specify this optional parameter, the API returns only the aliases that are pointing to the specific Lambda function version, otherwise the API returns all of the aliases created for the Lambda function.

  

``--marker`` (string)


  Optional string. An opaque pagination token returned from a previous ``list-aliases`` operation. If present, indicates where to continue the listing.

  

``--max-items`` (integer)


  Optional integer. Specifies the maximum number of aliases to return in response. This parameter value must be greater than 0.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

NextMarker -> (string)

  

  A string, present if there are more aliases.

  

  

Aliases -> (list)

  

  A list of aliases.

  

  (structure)

    

    Provides configuration information about a Lambda function version alias.

    

    AliasArn -> (string)

      

      Lambda function ARN that is qualified using the alias name as the suffix. For example, if you create an alias called ``BETA`` that points to a helloworld function version, the ARN is ``arn:aws:lambda:aws-regions:acct-id:function:helloworld:BETA`` .

      

      

    Name -> (string)

      

      Alias name.

      

      

    FunctionVersion -> (string)

      

      Function version to which the alias points.

      

      

    Description -> (string)

      

      Alias description.

      

      

    

  



.. _Introduction to AWS Lambda Aliases: http://docs.aws.amazon.com/lambda/latest/dg/aliases-intro.html
