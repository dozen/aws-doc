[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect describe-locations:


******************
describe-locations
******************



===========
Description
===========



Returns the list of AWS Direct Connect locations in the current AWS region. These are the locations that may be selected when calling create-connection or CreateInterconnect.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/DescribeLocations>`_


========
Synopsis
========

::

    describe-locations
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list AWS Direct Connect partners and locations**

The following ``describe-locations`` command lists AWS Direct Connect partners and locations in the current region::

  aws directconnect describe-locations

Output::

  {
      "locations": [
          {
              "locationName": "NAP do Brasil, Barueri, Sao Paulo", 
              "locationCode": "TNDB"
          }, 
          {
              "locationName": "Tivit - Site Transamerica (Sao Paulo)", 
              "locationCode": "TIVIT"
          }
      ]
  }

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

      

      

    

  

