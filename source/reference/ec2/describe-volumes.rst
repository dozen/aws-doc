[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-volumes:


****************
describe-volumes
****************



===========
Description
===========



Describes the specified EBS volumes.

 

If you are describing a long list of volumes, you can paginate the output to make the list more manageable. The ``MaxResults`` parameter sets the maximum number of results returned in a single page. If the list of results exceeds your ``MaxResults`` value, then that number of results is returned along with a ``NextToken`` value that can be passed to a subsequent ``describe-volumes`` request to retrieve the remaining results.

 

For more information about EBS volumes, see `Amazon EBS Volumes`_ in the *Amazon Elastic Compute Cloud User Guide* .



``describe-volumes`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Volumes``


========
Synopsis
========

::

    describe-volumes
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

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``attachment.attach-time`` - The time stamp when the attachment initiated. 
   
  * ``attachment.delete-on-termination`` - Whether the volume is deleted on instance termination. 
   
  * ``attachment.device`` - The device name that is exposed to the instance (for example, ``/dev/sda1`` ). 
   
  * ``attachment.instance-id`` - The ID of the instance the volume is attached to. 
   
  * ``attachment.status`` - The attachment state (``attaching`` | ``attached`` | ``detaching`` | ``detached`` ). 
   
  * ``availability-zone`` - The Availability Zone in which the volume was created. 
   
  * ``create-time`` - The time stamp when the volume was created. 
   
  * ``encrypted`` - The encryption status of the volume. 
   
  * ``size`` - The size of the volume, in GiB. 
   
  * ``snapshot-id`` - The snapshot from which the volume was created. 
   
  * ``status`` - The status of the volume (``creating`` | ``available`` | ``in-use`` | ``deleting`` | ``deleted`` | ``error`` ). 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``volume-id`` - The volume ID. 
   
  * ``volume-type`` - The Amazon EBS volume type. This can be ``gp2`` for General Purpose (SSD) volumes, ``io1`` for Provisioned IOPS (SSD) volumes, or ``standard`` for Magnetic volumes. 
   

  



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

**To describe all volumes**

This example command describes all of your volumes in the default region.

Command::

  aws ec2 describe-volumes

Output::

   {
       "Volumes": [
           {
               "AvailabilityZone": "us-east-1a",
               "Attachments": [
                   {
                       "AttachTime": "2013-12-18T22:35:00.000Z",
                       "InstanceId": "i-abe041d4",
                       "VolumeId": "vol-21083656",
                       "State": "attached",
                       "DeleteOnTermination": true,
                       "Device": "/dev/sda1"
                   }
               ],
               "VolumeType": "standard",
               "VolumeId": "vol-21083656",
               "State": "in-use",
               "SnapshotId": "snap-b4ef17a9",
               "CreateTime": "2013-12-18T22:35:00.084Z",
               "Size": 8
           },
           {
               "AvailabilityZone": "us-east-1a",
               "Attachments": [],
               "VolumeType": "io1",
               "VolumeId": "vol-2725bc51",
               "State": "available",
               "Iops": 1000,
               "SnapshotId": null,
               "CreateTime": "2014-02-27T00:02:41.791Z",
               "Size": 100
           }
       ]
   }

**To describe volumes that are attached to a specific instance**

This example command describes all volumes that are both attached to the instance with the ID i-abe041d4 and set to delete when the instance terminates.

Command::

  aws ec2 describe-volumes --region us-east-1 --filters Name=attachment.instance-id,Values=i-abe041d4 Name=attachment.delete-on-termination,Values=true

Output::

   {
       "Volumes": [
           {
               "AvailabilityZone": "us-east-1a",
               "Attachments": [
                   {
                       "AttachTime": "2013-12-18T22:35:00.000Z",
                       "InstanceId": "i-abe041d4",
                       "VolumeId": "vol-21083656",
                       "State": "attached",
                       "DeleteOnTermination": true,
                       "Device": "/dev/sda1"
                   }
               ],
               "VolumeType": "standard",
               "VolumeId": "vol-21083656",
               "State": "in-use",
               "SnapshotId": "snap-b4ef17a9",
               "CreateTime": "2013-12-18T22:35:00.084Z",
               "Size": 8
           }
       ]
   }
 
**To describe tagged volumes and filter the output**

This example command describes all volumes that have the tag key ``Name`` and a value that begins with ``Test``. The output is filtered to display only the tags and IDs of the volumes. 

Command::

  aws ec2 describe-volumes --filters Name=tag-key,Values="Name" Name=tag-value,Values="Test*" --query 'Volumes[*].{ID:VolumeId,Tag:Tags}'

Output::

   [
     {
        "Tag": [
            {
                "Value": "Test2", 
                "Key": "Name"
            }
        ], 
        "ID": "vol-9de9e9d9"
    }, 
    {
        "Tag": [
            {
                "Value": "Test1", 
                "Key": "Name"
            }
        ], 
        "ID": "vol-b2242df9"
     }
   ]



======
Output
======

Volumes -> (list)

  

  Information about the volumes.

  

  (structure)

    

    Describes a volume.

    

    VolumeId -> (string)

      

      The ID of the volume.

      

      

    Size -> (integer)

      

      The size of the volume, in GiBs.

      

      

    SnapshotId -> (string)

      

      The snapshot from which the volume was created, if applicable.

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone for the volume.

      

      

    State -> (string)

      

      The volume state.

      

      

    CreateTime -> (timestamp)

      

      The time stamp when volume creation was initiated.

      

      

    Attachments -> (list)

      

      Information about the volume attachments.

      

      (structure)

        

        Describes volume attachment details.

        

        VolumeId -> (string)

          

          The ID of the volume.

          

          

        InstanceId -> (string)

          

          The ID of the instance.

          

          

        Device -> (string)

          

          The device name.

          

          

        State -> (string)

          

          The attachment state of the volume.

          

          

        AttachTime -> (timestamp)

          

          The time stamp when the attachment initiated.

          

          

        DeleteOnTermination -> (boolean)

          

          Indicates whether the EBS volume is deleted on instance termination.

          

          

        

      

    Tags -> (list)

      

      Any tags assigned to the volume.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag. 

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    VolumeType -> (string)

      

      The volume type. This can be ``gp2`` for General Purpose (SSD) volumes, ``io1`` for Provisioned IOPS (SSD) volumes, or ``standard`` for Magnetic volumes.

      

      

    Iops -> (integer)

      

      The number of I/O operations per second (IOPS) that the volume supports. For Provisioned IOPS (SSD) volumes, this represents the number of IOPS that are provisioned for the volume. For General Purpose (SSD) volumes, this represents the baseline performance of the volume and the rate at which the volume accumulates I/O credits for bursting. For more information on General Purpose (SSD) baseline performance, I/O credits, and bursting, see `Amazon EBS Volume Types`_ in the *Amazon Elastic Compute Cloud User Guide* .

       

      Constraint: Range is 100 to 20000 for Provisioned IOPS (SSD) volumes and 3 to 10000 for General Purpose (SSD) volumes.

       

      Condition: This parameter is required for requests to create ``io1`` volumes; it is not used in requests to create ``standard`` or ``gp2`` volumes.

      

      

    Encrypted -> (boolean)

      

      Indicates whether the volume will be encrypted.

      

      

    KmsKeyId -> (string)

      

      The full ARN of the AWS Key Management Service (AWS KMS) customer master key (CMK) that was used to protect the volume encryption key for the volume.

      

      

    

  

NextToken -> (string)

  

  The ``NextToken`` value to include in a future ``describe-volumes`` request. When the results of a ``describe-volumes`` request exceed ``MaxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  



.. _Amazon EBS Volume Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html
.. _Amazon EBS Volumes: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumes.html
