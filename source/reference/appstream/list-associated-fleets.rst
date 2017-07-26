[ :ref:`aws <cli:aws>` . :ref:`appstream <cli:aws appstream>` ]

.. _cli:aws appstream list-associated-fleets:


**********************
list-associated-fleets
**********************



===========
Description
===========



Lists all fleets associated with the stack.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/appstream-2016-12-01/ListAssociatedFleets>`_


========
Synopsis
========

::

    list-associated-fleets
  --stack-name <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name of the stack whose associated fleets are listed.

  

``--next-token`` (string)


  The pagination token to use to retrieve the next page of results for this operation. If this value is null, it retrieves the first page.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Names -> (list)

  

  The names of associated fleets.

  

  (string)

    

    

  

NextToken -> (string)

  

  The pagination token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

  

  

