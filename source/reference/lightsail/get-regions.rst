[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-regions:


***********
get-regions
***********



===========
Description
===========



Returns a list of all valid regions for Amazon Lightsail. Use the ``include availability zones`` parameter to also return the availability zones in a region.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetRegions>`_


========
Synopsis
========

::

    get-regions
  [--include-availability-zones | --no-include-availability-zones]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--include-availability-zones`` | ``--no-include-availability-zones`` (boolean)


  A Boolean value indicating whether to also include Availability Zones in your get regions request. Availability Zones are indicated with a letter: e.g., ``us-east-1a`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

regions -> (list)

  

  An array of key-value pairs containing information about your get regions request.

  

  (structure)

    

    Describes the AWS Region.

    

    continentCode -> (string)

      

      The continent code (e.g., ``NA`` , meaning North America).

      

      

    description -> (string)

      

      The description of the AWS Region (e.g., ``This region is recommended to serve users in the eastern United States and eastern Canada`` ).

      

      

    displayName -> (string)

      

      The display name (e.g., ``Virginia`` ).

      

      

    name -> (string)

      

      The region name (e.g., ``us-east-1`` ).

      

      

    availabilityZones -> (list)

      

      The Availability Zones. Follows the format ``us-east-1a`` (case-sensitive).

      

      (structure)

        

        Describes an Availability Zone.

        

        zoneName -> (string)

          

          The name of the Availability Zone. The format is ``us-east-1a`` (case-sensitive).

          

          

        state -> (string)

          

          The state of the Availability Zone.

          

          

        

      

    

  

