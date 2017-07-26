[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift update-fleet-port-settings:


**************************
update-fleet-port-settings
**************************



===========
Description
===========



Updates port settings for a fleet. To update settings, specify the fleet ID to be updated and list the permissions you want to update. List the permissions you want to add in ``InboundPermissionAuthorizations`` , and permissions you want to remove in ``InboundPermissionRevocations`` . Permissions to be removed must match existing fleet permissions. If successful, the fleet ID for the updated fleet is returned.

 

Fleet-related operations include:

 

 
*  create-fleet   
 
*  list-fleets   
 
* Describe fleets: 

   
  *  describe-fleet-attributes   
   
  *  describe-fleet-port-settings   
   
  *  describe-fleet-utilization   
   
  *  describe-runtime-configuration   
   
  *  describe-fleet-events   
   

 
 
* Update fleets: 

   
  *  update-fleet-attributes   
   
  *  update-fleet-capacity   
   
  *  update-fleet-port-settings   
   
  *  update-runtime-configuration   
   

 
 
* Manage fleet capacity: 

   
  *  describe-fleet-capacity   
   
  *  update-fleet-capacity   
   
  *  put-scaling-policy (automatic scaling) 
   
  *  describe-scaling-policies (automatic scaling) 
   
  *  delete-scaling-policy (automatic scaling) 
   
  *  describe-ec2-instance-limits   
   

 
 
*  delete-fleet   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/UpdateFleetPortSettings>`_


========
Synopsis
========

::

    update-fleet-port-settings
  --fleet-id <value>
  [--inbound-permission-authorizations <value>]
  [--inbound-permission-revocations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet to update port settings for.

  

``--inbound-permission-authorizations`` (list)


  Collection of port settings to be added to the fleet record.

  



Shorthand Syntax::

    FromPort=integer,ToPort=integer,IpRange=string,Protocol=string ...




JSON Syntax::

  [
    {
      "FromPort": integer,
      "ToPort": integer,
      "IpRange": "string",
      "Protocol": "TCP"|"UDP"
    }
    ...
  ]



``--inbound-permission-revocations`` (list)


  Collection of port settings to be removed from the fleet record.

  



Shorthand Syntax::

    FromPort=integer,ToPort=integer,IpRange=string,Protocol=string ...




JSON Syntax::

  [
    {
      "FromPort": integer,
      "ToPort": integer,
      "IpRange": "string",
      "Protocol": "TCP"|"UDP"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FleetId -> (string)

  

  Unique identifier for a fleet that was updated.

  

  

