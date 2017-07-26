[ :ref:`aws <cli:aws>` . :ref:`shield <cli:aws shield>` ]

.. _cli:aws shield describe-attack:


***************
describe-attack
***************



===========
Description
===========



Describes the details of a DDoS attack. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/shield-2016-06-02/DescribeAttack>`_


========
Synopsis
========

::

    describe-attack
  --attack-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attack-id`` (string)


  The unique identifier (ID) for the attack that to be described.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Attack -> (structure)

  

  The attack that is described.

  

  AttackId -> (string)

    

    The unique identifier (ID) of the attack.

    

    

  ResourceArn -> (string)

    

    The ARN (Amazon Resource Name) of the resource that was attacked.

    

    

  SubResources -> (list)

    

    If applicable, additional detail about the resource being attacked, for example, IP address or URL.

    

    (structure)

      

      The attack information for the specified SubResource.

      

      Type -> (string)

        

        The ``SubResource`` type.

        

        

      Id -> (string)

        

        The unique identifier (ID) of the ``SubResource`` .

        

        

      AttackVectors -> (list)

        

        The list of attack types and associated counters.

        

        (structure)

          

          A summary of information about the attack.

          

          VectorType -> (string)

            

            The attack type, for example, SNMP reflection or SYN flood.

            

            

          VectorCounters -> (list)

            

            The list of counters that describe the details of the attack.

            

            (structure)

              

              The counter that describes a DDoS attack.

              

              Name -> (string)

                

                The counter name.

                

                

              Max -> (double)

                

                The maximum value of the counter for a specified time period.

                

                

              Average -> (double)

                

                The average value of the counter for a specified time period.

                

                

              Sum -> (double)

                

                The total of counter values for a specified time period.

                

                

              N -> (integer)

                

                The number of counters for a specified time period.

                

                

              Unit -> (string)

                

                The unit of the counters.

                

                

              

            

          

        

      Counters -> (list)

        

        The counters that describe the details of the attack.

        

        (structure)

          

          The counter that describes a DDoS attack.

          

          Name -> (string)

            

            The counter name.

            

            

          Max -> (double)

            

            The maximum value of the counter for a specified time period.

            

            

          Average -> (double)

            

            The average value of the counter for a specified time period.

            

            

          Sum -> (double)

            

            The total of counter values for a specified time period.

            

            

          N -> (integer)

            

            The number of counters for a specified time period.

            

            

          Unit -> (string)

            

            The unit of the counters.

            

            

          

        

      

    

  StartTime -> (timestamp)

    

    The time the attack started, in the format 2016-12-16T13:50Z.

    

    

  EndTime -> (timestamp)

    

    The time the attack ended, in the format 2016-12-16T13:50Z.

    

    

  AttackCounters -> (list)

    

    List of counters that describe the attack for the specified time period.

    

    (structure)

      

      The counter that describes a DDoS attack.

      

      Name -> (string)

        

        The counter name.

        

        

      Max -> (double)

        

        The maximum value of the counter for a specified time period.

        

        

      Average -> (double)

        

        The average value of the counter for a specified time period.

        

        

      Sum -> (double)

        

        The total of counter values for a specified time period.

        

        

      N -> (integer)

        

        The number of counters for a specified time period.

        

        

      Unit -> (string)

        

        The unit of the counters.

        

        

      

    

  Mitigations -> (list)

    

    List of mitigation actions taken for the attack.

    

    (structure)

      

      The mitigation applied to a DDoS attack.

      

      MitigationName -> (string)

        

        The name of the mitigation taken for this attack.

        

        

      

    

  

