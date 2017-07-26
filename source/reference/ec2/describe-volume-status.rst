[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-volume-status:


**********************
describe-volume-status
**********************



===========
Description
===========



Describes the status of the specified volumes. Volume status provides the result of the checks performed on your volumes to determine events that can impair the performance of your volumes. The performance of a volume can be affected if an issue occurs on the volume's underlying host. If the volume's underlying host experiences a power outage or system issue, after the system is restored, there could be data inconsistencies on the volume. Volume events notify you if this occurs. Volume actions notify you if any action needs to be taken in response to the event.

 

The ``describe-volume-status`` operation provides the following information about the specified volumes:

 

*Status* : Reflects the current status of the volume. The possible values are ``ok`` , ``impaired`` , ``warning`` , or ``insufficient-data`` . If all checks pass, the overall status of the volume is ``ok`` . If the check fails, the overall status is ``impaired`` . If the status is ``insufficient-data`` , then the checks may still be taking place on your volume at the time. We recommend that you retry the request. For more information on volume status, see `Monitoring the Status of Your Volumes`_ .

 

*Events* : Reflect the cause of a volume status and may require you to take action. For example, if your volume returns an ``impaired`` status, then the volume event might be ``potential-data-inconsistency`` . This means that your volume has been affected by an issue with the underlying host, has all I/O operations disabled, and may have inconsistent data.

 

*Actions* : Reflect the actions you may have to take in response to an event. For example, if the status of the volume is ``impaired`` and the volume event shows ``potential-data-inconsistency`` , then the action shows ``enable-volume-io`` . This means that you may want to enable the I/O operations for the volume by calling the  enable-volume-io action and then check the volume for data consistency.

 

.. note::

   

  Volume status is based on the volume status checks, and does not reflect the volume state. Therefore, volume status does not indicate volumes in the ``error`` state (for example, when a volume is incapable of accepting I/O.)

   



``describe-volume-status`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``VolumeStatuses``


========
Synopsis
========

::

    describe-volume-status
  [--dry-run | --no-dry-run]
  [--volume-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--volume-ids`` (list)


  One or more volume IDs.

   

  Default: Describes all your volumes.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``action.code`` - The action code for the event (for example, ``enable-volume-io`` ). 
   
  * ``action.description`` - A description of the action. 
   
  * ``action.event-id`` - The event ID associated with the action. 
   
  * ``availability-zone`` - The Availability Zone of the instance. 
   
  * ``event.description`` - A description of the event. 
   
  * ``event.event-id`` - The event ID. 
   
  * ``event.event-type`` - The event type (for ``io-enabled`` : ``passed`` | ``failed`` ; for ``io-performance`` : ``io-performance:degraded`` | ``io-performance:severely-degraded`` | ``io-performance:stalled`` ). 
   
  * ``event.not-after`` - The latest end time for the event. 
   
  * ``event.not-before`` - The earliest start time for the event. 
   
  * ``volume-status.details-name`` - The cause for ``volume-status.status`` (``io-enabled`` | ``io-performance`` ). 
   
  * ``volume-status.details-status`` - The status of ``volume-status.details-name`` (for ``io-enabled`` : ``passed`` | ``failed`` ; for ``io-performance`` : ``normal`` | ``degraded`` | ``severely-degraded`` | ``stalled`` ). 
   
  * ``volume-status.status`` - The status of the volume (``ok`` | ``impaired`` | ``warning`` | ``insufficient-data`` ). 
   

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe the status of a single volume**

This example command describes the status for the volume ``vol-2725bc51``.

Command::

  aws ec2 describe-volume-status --volume-ids vol-2725bc51

Output::

   {
       "VolumeStatuses": [
           {
               "VolumeStatus": {
                   "Status": "ok",
                   "Details": [
                       {
                           "Status": "passed",
                           "Name": "io-enabled"
                       },
                       {
                           "Status": "not-applicable",
                           "Name": "io-performance"
                       }
                   ]
               },
               "AvailabilityZone": "us-east-1a",
               "VolumeId": "vol-2725bc51",
               "Actions": [],
               "Events": []
           }
       ]
   }

**To describe the status of impaired volumes**

This example command describes the status for all volumes that are impaired. In this example output, there are no impaired volumes.

Command::

  aws ec2 describe-volume-status --filters Name=volume-status.status,Values=impaired

Output::

   {
       "VolumeStatuses": []
   }

If you have a volume with a failed status check (status is impaired), see `Working with an Impaired Volume`_ in the *Amazon EC2 User Guide*.

.. _`Working with an Impaired Volume`: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring-volume-status.html#work_volumes_impaired


======
Output
======

VolumeStatuses -> (list)

  

  A list of volumes.

  

  (structure)

    

    Describes the volume status.

    

    VolumeId -> (string)

      

      The volume ID.

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone of the volume.

      

      

    VolumeStatus -> (structure)

      

      The volume status.

      

      Status -> (string)

        

        The status of the volume.

        

        

      Details -> (list)

        

        The details of the volume status.

        

        (structure)

          

          Describes a volume status.

          

          Name -> (string)

            

            The name of the volume status.

            

            

          Status -> (string)

            

            The intended status of the volume status.

            

            

          

        

      

    Events -> (list)

      

      A list of events associated with the volume.

      

      (structure)

        

        Describes a volume status event.

        

        EventType -> (string)

          

          The type of this event.

          

          

        Description -> (string)

          

          A description of the event.

          

          

        NotBefore -> (timestamp)

          

          The earliest start time of the event.

          

          

        NotAfter -> (timestamp)

          

          The latest end time of the event.

          

          

        EventId -> (string)

          

          The ID of this event.

          

          

        

      

    Actions -> (list)

      

      The details of the operation.

      

      (structure)

        

        Describes a volume status operation code.

        

        Code -> (string)

          

          The code identifying the operation, for example, ``enable-volume-io`` .

          

          

        Description -> (string)

          

          A description of the operation.

          

          

        EventType -> (string)

          

          The event type associated with this operation.

          

          

        EventId -> (string)

          

          The ID of the event associated with this operation.

          

          

        

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  



.. _Monitoring the Status of Your Volumes: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring-volume-status.html
