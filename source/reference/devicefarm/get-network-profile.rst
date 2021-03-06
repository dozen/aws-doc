[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-network-profile:


*******************
get-network-profile
*******************



===========
Description
===========



Returns information about a network profile.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/GetNetworkProfile>`_


========
Synopsis
========

::

    get-network-profile
  --arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The Amazon Resource Name (ARN) of the network profile you want to return information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

networkProfile -> (structure)

  

  The network profile.

  

  arn -> (string)

    

    The Amazon Resource Name (ARN) of the network profile.

    

    

  name -> (string)

    

    The name of the network profile.

    

    

  description -> (string)

    

    The description of the network profile.

    

    

  type -> (string)

    

    The type of network profile. Valid values are listed below.

    

    

  uplinkBandwidthBits -> (long)

    

    The data throughput rate in bits per second, as an integer from 0 to 104857600.

    

    

  downlinkBandwidthBits -> (long)

    

    The data throughput rate in bits per second, as an integer from 0 to 104857600.

    

    

  uplinkDelayMs -> (long)

    

    Delay time for all packets to destination in milliseconds as an integer from 0 to 2000.

    

    

  downlinkDelayMs -> (long)

    

    Delay time for all packets to destination in milliseconds as an integer from 0 to 2000.

    

    

  uplinkJitterMs -> (long)

    

    Time variation in the delay of received packets in milliseconds as an integer from 0 to 2000.

    

    

  downlinkJitterMs -> (long)

    

    Time variation in the delay of received packets in milliseconds as an integer from 0 to 2000.

    

    

  uplinkLossPercent -> (integer)

    

    Proportion of transmitted packets that fail to arrive from 0 to 100 percent.

    

    

  downlinkLossPercent -> (integer)

    

    Proportion of received packets that fail to arrive from 0 to 100 percent.

    

    

  

