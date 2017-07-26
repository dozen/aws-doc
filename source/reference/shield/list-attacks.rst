[ :ref:`aws <cli:aws>` . :ref:`shield <cli:aws shield>` ]

.. _cli:aws shield list-attacks:


************
list-attacks
************



===========
Description
===========



Returns all ongoing DDoS attacks or all DDoS attacks during a specified time period.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/shield-2016-06-02/ListAttacks>`_


========
Synopsis
========

::

    list-attacks
  [--resource-arns <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arns`` (list)


  The ARN (Amazon Resource Name) of the resource that was attacked. If this is left blank, all applicable resources for this account will be included.

  



Syntax::

  "string" "string" ...



``--start-time`` (structure)


  The time period for the attacks.

  



Shorthand Syntax::

    FromInclusive=timestamp,ToExclusive=timestamp




JSON Syntax::

  {
    "FromInclusive": timestamp,
    "ToExclusive": timestamp
  }



``--end-time`` (structure)


  The end of the time period for the attacks.

  



Shorthand Syntax::

    FromInclusive=timestamp,ToExclusive=timestamp




JSON Syntax::

  {
    "FromInclusive": timestamp,
    "ToExclusive": timestamp
  }



``--next-token`` (string)


  The ``ListAttacksRequest.NextMarker`` value from a previous call to ``ListAttacksRequest`` . Pass null if this is the first call.

  

``--max-results`` (integer)


  The maximum number of  AttackSummary objects to be returned. If this is left blank, the first 20 results will be returned.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AttackSummaries -> (list)

  

  The attack information for the specified time range.

  

  (structure)

    

    Summarizes all DDoS attacks for a specified time period.

    

    AttackId -> (string)

      

      The unique identifier (ID) of the attack.

      

      

    ResourceArn -> (string)

      

      The ARN (Amazon Resource Name) of the resource that was attacked.

      

      

    StartTime -> (timestamp)

      

      The start time of the attack, in the format 2016-12-16T13:50Z.

      

      

    EndTime -> (timestamp)

      

      The end time of the attack, in the format 2016-12-16T13:50Z.

      

      

    AttackVectors -> (list)

      

      The list of attacks for a specified time period.

      

      (structure)

        

        Describes the attack.

        

        VectorType -> (string)

          

          The attack type, for example, SNMP reflection or SYN flood.

          

          

        

      

    

  

NextToken -> (string)

  

  The token returned by a previous call to indicate that there is more data available. If not null, more results are available. Pass this value for the ``NextMarker`` parameter in a subsequent call to ``list-attacks`` to retrieve the next set of items.

  

  

