[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-spot-fleet-request-history:


***********************************
describe-spot-fleet-request-history
***********************************



===========
Description
===========



Describes the events for the specified Spot fleet request during the specified time.

 

Spot fleet events are delayed by up to 30 seconds before they can be described. This ensures that you can query by the last evaluated time and not miss a recorded event.



========
Synopsis
========

::

    describe-spot-fleet-request-history
  [--dry-run | --no-dry-run]
  --spot-fleet-request-id <value>
  [--event-type <value>]
  --start-time <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-fleet-request-id`` (string)


  The ID of the Spot fleet request.

  

``--event-type`` (string)


  The type of events to describe. By default, all events are described.

  

  Possible values:

  
  *   ``instanceChange``

  
  *   ``fleetRequestChange``

  
  *   ``error``

  

  

``--start-time`` (timestamp)


  The starting date and time for the events, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z).

  

``--next-token`` (string)


  The token for the next set of results.

  

``--max-results`` (integer)


  The maximum number of results to return in a single call. Specify a value between 1 and 1000. The default value is 1000. To retrieve the remaining results, make another call with the returned ``NextToken`` value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe Spot fleet history**

This example command returns the history for the specified Spot fleet starting at the specified time.

Command::

  aws ec2 describe-spot-fleet-request-history --spot-fleet-request-id sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE --start-time 2015-05-26T00:00:00Z

The following example output shows the successful launches of two Spot Instances for the Spot fleet.
  
Output::

  {
    "HistoryRecords": [
        {
            "Timestamp": "2015-05-26T23:17:20.697Z",
            "EventInformation": {
                "EventSubType": "submitted"
            },
            "EventType": "fleetRequestChange"
        },
        {
            "Timestamp": "2015-05-26T23:17:20.873Z",
            "EventInformation": {
                "EventSubType": "active"
            },
            "EventType": "fleetRequestChange"
        },
        {
            "Timestamp": "2015-05-26T23:21:21.712Z",
            "EventInformation": {
                "InstanceId": "i-3a52c1cd",
                "EventSubType": "launched"
            },
            "EventType": "instanceChange"
        },
        {
            "Timestamp": "2015-05-26T23:21:21.816Z",
            "EventInformation": {
                "InstanceId": "i-3852c1cf",
                "EventSubType": "launched"
            },
            "EventType": "instanceChange"
        }
    ],
    "SpotFleetRequestId": "sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE",
    "NextToken": "CpHNsscimcV5oH7bSbub03CI2Qms5+ypNpNm+53MNlR0YcXAkp0xFlfKf91yVxSExmbtma3awYxMFzNA663ZskT0AHtJ6TCb2Z8bQC2EnZgyELbymtWPfpZ1ZbauVg+P+TfGlWxWWB/Vr5dk5d4LfdgA/DRAHUrYgxzrEXAMPLE=",
    "StartTime": "2015-05-26T00:00:00Z"  
  }


======
Output
======

SpotFleetRequestId -> (string)

  

  The ID of the Spot fleet request.

  

  

StartTime -> (timestamp)

  

  The starting date and time for the events, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z).

  

  

LastEvaluatedTime -> (timestamp)

  

  The last date and time for the events, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z). All records up to this time were retrieved.

   

  If ``nextToken`` indicates that there are more results, this value is not present.

  

  

HistoryRecords -> (list)

  

  Information about the events in the history of the Spot fleet request.

  

  (structure)

    

    Describes an event in the history of the Spot fleet request.

    

    Timestamp -> (timestamp)

      

      The date and time of the event, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z).

      

      

    EventType -> (string)

      

      The event type.

       

       
      * ``error`` - Indicates an error with the Spot fleet request. 
       
      * ``fleetRequestChange`` - Indicates a change in the status or configuration of the Spot fleet request. 
       
      * ``instanceChange`` - Indicates that an instance was launched or terminated. 
       

      

      

    EventInformation -> (structure)

      

      Information about the event.

      

      InstanceId -> (string)

        

        The ID of the instance. This information is available only for ``instanceChange`` events.

        

        

      EventSubType -> (string)

        

        The event.

         

        The following are the ``error`` events.

         

         
        * ``iamFleetRoleInvalid`` - The Spot fleet did not have the required permissions either to launch or terminate an instance. 
         
        * ``launchSpecTemporarilyBlacklisted`` - The configuration is not valid and several attempts to launch instances have failed. For more information, see the description of the event. 
         
        * ``spotFleetRequestConfigurationInvalid`` - The configuration is not valid. For more information, see the description of the event. 
         
        * ``spotInstanceCountLimitExceeded`` - You've reached the limit on the number of Spot instances that you can launch. 
         

         

        The following are the ``fleetRequestChange`` events.

         

         
        * ``active`` - The Spot fleet has been validated and Amazon EC2 is attempting to maintain the target number of running Spot instances. 
         
        * ``cancelled`` - The Spot fleet is canceled and has no running Spot instances. The Spot fleet will be deleted two days after its instances were terminated. 
         
        * ``cancelled_running`` - The Spot fleet is canceled and will not launch additional Spot instances, but its existing Spot instances continue to run until they are interrupted or terminated. 
         
        * ``cancelled_terminating`` - The Spot fleet is canceled and its Spot instances are terminating. 
         
        * ``expired`` - The Spot fleet request has expired. A subsequent event indicates that the instances were terminated, if the request was created with ``TerminateInstancesWithExpiration`` set. 
         
        * ``modify_in_progress`` - A request to modify the Spot fleet request was accepted and is in progress. 
         
        * ``modify_successful`` - The Spot fleet request was modified. 
         
        * ``price_update`` - The bid price for a launch configuration was adjusted because it was too high. This change is permanent. 
         
        * ``submitted`` - The Spot fleet request is being evaluated and Amazon EC2 is preparing to launch the target number of Spot instances. 
         

         

        The following are the ``instanceChange`` events.

         

         
        * ``launched`` - A bid was fulfilled and a new instance was launched. 
         
        * ``terminated`` - An instance was terminated by the user. 
         

        

        

      EventDescription -> (string)

        

        The description of the event.

        

        

      

    

  

NextToken -> (string)

  

  The token required to retrieve the next set of results. This value is ``null`` when there are no more results to return.

  

  

