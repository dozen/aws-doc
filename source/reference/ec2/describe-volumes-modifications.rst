[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-volumes-modifications:


******************************
describe-volumes-modifications
******************************



===========
Description
===========



Reports the current modification status of EBS volumes.

 

Current-generation EBS volumes support modification of attributes including type, size, and (for ``io1`` volumes) IOPS provisioning while either attached to or detached from an instance. Following an action from the API or the console to modify a volume, the status of the modification may be ``modifying`` , ``optimizing`` , ``completed`` , or ``failed`` . If a volume has never been modified, then certain elements of the returned ``VolumeModification`` objects are null. 

 

You can also use CloudWatch Events to check the status of a modification to an EBS volume. For information about CloudWatch Events, see the `Amazon CloudWatch Events User Guide <http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/>`_ . For more information, see `Monitoring Volume Modifications" <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-expand-volume.html#monitoring_mods>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeVolumesModifications>`_


========
Synopsis
========

::

    describe-volumes-modifications
  [--dry-run | --no-dry-run]
  [--volume-ids <value>]
  [--filters <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--volume-ids`` (list)


  One or more volume IDs for which in-progress modifications will be described.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters. Supported filters: ``volume-id`` , ``modification-state`` , ``target-size`` , ``target-iops`` , ``target-volume-type`` , ``original-size`` , ``original-iops`` , ``original-volume-type`` , ``start-time`` . 

  



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



``--next-token`` (string)


  The ``nextToken`` value returned by a previous paginated request.

  

``--max-results`` (integer)


  The maximum number of results (up to a limit of 500) to be returned in a paginated request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

VolumesModifications -> (list)

  

  A list of returned  VolumeModification objects.

  

  (structure)

    

    Describes the modification status of an EBS volume.

     

    If the volume has never been modified, some element values will be null.

    

    VolumeId -> (string)

      

      ID of the volume being modified.

      

      

    ModificationState -> (string)

      

      Current state of modification. Modification state is null for unmodified volumes. 

      

      

    StatusMessage -> (string)

      

      Generic status message on modification progress or failure.

      

      

    TargetSize -> (integer)

      

      Target size of the volume being modified.

      

      

    TargetIops -> (integer)

      

      Target IOPS rate of the volume being modified.

      

      

    TargetVolumeType -> (string)

      

      Target EBS volume type of the volume being modified.

      

      

    OriginalSize -> (integer)

      

      Original size of the volume being modified.

      

      

    OriginalIops -> (integer)

      

      Original IOPS rate of the volume being modified.

      

      

    OriginalVolumeType -> (string)

      

      Original EBS volume type of the volume being modified.

      

      

    Progress -> (long)

      

      Modification progress from 0 to 100%.

      

      

    StartTime -> (timestamp)

      

      Modification start time 

      

      

    EndTime -> (timestamp)

      

      Modification completion or failure time.

      

      

    

  

NextToken -> (string)

  

  Token for pagination, null if there are no more results 

  

  

