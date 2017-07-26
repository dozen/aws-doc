[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb describe-time-to-live:


*********************
describe-time-to-live
*********************



===========
Description
===========



Gives a description of the Time to Live (TTL) status on the specified table. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/DescribeTimeToLive>`_


========
Synopsis
========

::

    describe-time-to-live
  --table-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--table-name`` (string)


  The name of the table to be described.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TimeToLiveDescription -> (structure)

  

  

  

  TimeToLiveStatus -> (string)

    

    The Time to Live status for the table.

    

    

  AttributeName -> (string)

    

    The name of the Time to Live attribute for items in the table.

    

    

  

