[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-availability-zones:


***************************
describe-availability-zones
***************************



===========
Description
===========



Describes one or more of the Availability Zones that are available to you. The results include zones only for the region you're currently using. If there is an event impacting an Availability Zone, you can use this request to view the state and any provided message for that Availability Zone.

 

For more information, see `Regions and Availability Zones <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeAvailabilityZones>`_


========
Synopsis
========

::

    describe-availability-zones
  [--filters <value>]
  [--zone-names <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``message`` - Information about the Availability Zone. 
   
  * ``region-name`` - The name of the region for the Availability Zone (for example, ``us-east-1`` ). 
   
  * ``state`` - The state of the Availability Zone (``available`` | ``information`` | ``impaired`` | ``unavailable`` ). 
   
  * ``zone-name`` - The name of the Availability Zone (for example, ``us-east-1a`` ). 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--zone-names`` (list)


  The names of one or more Availability Zones.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your Availability Zones**

This example describes the Availability Zones that are available to you. The response includes Availability Zones only for the current region.

Command::

  aws ec2 describe-availability-zones

Output::

  {
      "AvailabilityZones": [
          {
              "State": "available",
              "RegionName": "us-east-1",
              "Messages": [],
              "ZoneName": "us-east-1b"
          },
          {
              "State": "available",
              "RegionName": "us-east-1",
              "Messages": [],
              "ZoneName": "us-east-1c"
          },
          {
              "State": "available",
              "RegionName": "us-east-1",
              "Messages": [],
              "ZoneName": "us-east-1d"
          }
      ]
  }


======
Output
======

AvailabilityZones -> (list)

  

  Information about one or more Availability Zones.

  

  (structure)

    

    Describes an Availability Zone.

    

    State -> (string)

      

      The state of the Availability Zone.

      

      

    Messages -> (list)

      

      Any messages about the Availability Zone.

      

      (structure)

        

        Describes a message about an Availability Zone.

        

        Message -> (string)

          

          The message about the Availability Zone.

          

          

        

      

    RegionName -> (string)

      

      The name of the region.

      

      

    ZoneName -> (string)

      

      The name of the Availability Zone.

      

      

    

  

