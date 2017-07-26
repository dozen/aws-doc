[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` . :ref:`wait <cli:aws ec2 wait>` ]

.. _cli:aws ec2 wait volume-deleted:


**************
volume-deleted
**************



===========
Description
===========

Wait until JMESPath query Volumes[].State returns deleted for all elements when polling with ``describe-volumes``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

``volume-deleted`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Volumes``


========
Synopsis
========

::

    volume-deleted
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



======
Output
======

None