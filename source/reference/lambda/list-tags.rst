[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda list-tags:


*********
list-tags
*********



===========
Description
===========



Returns a list of tags assigned to a function when supplied the function ARN (Amazon Resource Name).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/ListTags>`_


========
Synopsis
========

::

    list-tags
  --resource <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource`` (string)


  The ARN (Amazon Resource Name) of the function.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Tags -> (map)

  

  The list of tags assigned to the function.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

