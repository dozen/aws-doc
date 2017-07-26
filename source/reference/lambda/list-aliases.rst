[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda list-aliases:


************
list-aliases
************



===========
Description
===========



Returns list of aliases created for a Lambda function. For each alias, the response includes information such as the alias ARN, description, alias name, and the function version to which it points. For more information, see `Introduction to AWS Lambda Aliases <http://docs.aws.amazon.com/lambda/latest/dg/aliases-intro.html>`_ .

 

This requires permission for the lambda:ListAliases action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/ListAliases>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--function-name`` (string)


  Lambda function name for which the alias is created. Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 characters in length.

  

``--function-version`` (string)


  If you specify this optional parameter, the API returns only the aliases that are pointing to the specific Lambda function version, otherwise the API returns all of the aliases created for the Lambda function.

  

``--marker`` (string)


  Optional string. An opaque pagination token returned from a previous ``list-aliases`` operation. If present, indicates where to continue the listing.

  

``--max-items`` (integer)


  Optional integer. Specifies the maximum number of aliases to return in response. This parameter value must be greater than 0.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    

  

