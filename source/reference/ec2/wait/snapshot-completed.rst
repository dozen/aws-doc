[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` . :ref:`wait <cli:aws ec2 wait>` ]

.. _cli:aws ec2 wait snapshot-completed:


******************
snapshot-completed
******************



===========
Description
===========

Wait until JMESPath query Snapshots[].State returns completed for all elements when polling with ``describe-snapshots``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

``snapshot-completed`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Snapshots``


========
Synopsis
========

::

    snapshot-completed
  [--dry-run | --no-dry-run]
  [--snapshot-ids <value>]
  [--owner-ids <value>]
  [--restorable-by-user-ids <value>]
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

  

``--snapshot-ids`` (list)


  One or more snapshot IDs.

   

  Default: Describes snapshots for which you have launch permissions.

  



Syntax::

  "string" "string" ...



``--owner-ids`` (list)


  Returns the snapshots owned by the specified owner. Multiple owners can be specified.

  



Syntax::

  "string" "string" ...



``--restorable-by-user-ids`` (list)


  One or more AWS accounts IDs that can create volumes from the snapshot.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``description`` - A description of the snapshot. 
   
  * ``owner-alias`` - The AWS account alias (for example, ``amazon`` ) that owns the snapshot. 
   
  * ``owner-id`` - The ID of the AWS account that owns the snapshot. 
   
  * ``progress`` - The progress of the snapshot, as a percentage (for example, 80%). 
   
  * ``snapshot-id`` - The snapshot ID. 
   
  * ``start-time`` - The time stamp when the snapshot was initiated. 
   
  * ``status`` - The status of the snapshot (``pending`` | ``completed`` | ``error`` ). 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``volume-id`` - The ID of the volume the snapshot is for. 
   
  * ``volume-size`` - The size of the volume, in GiB. 
   

  



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