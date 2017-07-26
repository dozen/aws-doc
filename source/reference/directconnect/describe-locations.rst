[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect describe-locations:


******************
describe-locations
******************



===========
Description
===========



Returns the list of AWS Direct Connect locations in the current AWS region. These are the locations that may be selected when calling create-connection or CreateInterconnect.



========
Synopsis
========

::

    describe-locations
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

locations -> (list)

  

  A list of colocation hubs where network providers have equipment. Most regions have multiple locations available.

  

  (structure)

    

    An AWS Direct Connect location where connections and interconnects can be requested.

    

    locationCode -> (string)

      

      The code used to indicate the AWS Direct Connect location.

      

      

    locationName -> (string)

      

      The name of the AWS Direct Connect location. The name includes the colocation partner name and the physical site of the lit building.

      

      

    

  

