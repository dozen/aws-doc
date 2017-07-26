[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-instance-patch-states:


******************************
describe-instance-patch-states
******************************



===========
Description
===========



Retrieves the high-level patch state of one or more instances.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeInstancePatchStates>`_


========
Synopsis
========

::

    describe-instance-patch-states
  --instance-ids <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-ids`` (list)


  The ID of the instance whose patch state information should be retrieved.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--max-results`` (integer)


  The maximum number of instances to return (per page).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the patch summary states for instances**

This example gets the patch summary states for an instance.

Command::

  aws ssm describe-instance-patch-states --instance-ids "i-08ee91c0b17045407" "i-09a618aec652973a9"

Output::

  {
    "InstancePatchStates": [
      {
		"OperationStartTime":"2016-12-09T05:00:00Z",
		"FailedCount":0,
		"InstanceId":"i-08ee91c0b17045407",
		"OwnerInformation":"",
		"NotApplicableCount":2077,
		"OperationEndTime":"2016-12-09T05:02:37Z",
		"PatchGroup":"Production",
		"InstalledOtherCount":186,
		"MissingCount":7,
		"SnapshotId":"b0e65479-79be-4288-9f88-81c96bc3ed5e",
		"Operation":"Scan",
		"InstalledCount":72
	  },
	  {
		"OperationStartTime":"2016-12-09T04:59:09Z",
		"FailedCount":0,
		"InstanceId":"i-09a618aec652973a9"
		"OwnerInformation":"",
		"NotApplicableCount":1637,
		"OperationEndTime":"2016-12-09T05:03:57Z",
		"PatchGroup":"Production",
		"InstalledOtherCount":388,
		"MissingCount":2,
		"SnapshotId":"b0e65479-79be-4288-9f88-81c96bc3ed5e",
		"Operation":"Scan",
		"InstalledCount":141
	  }
	]
  }


======
Output
======

InstancePatchStates -> (list)

  

  The high-level patch state for the requested instances.

  

  (structure)

    

    Defines the high-level patch compliance state for a managed instance, providing information about the number of installed, missing, not applicable, and failed patches along with metadata about the operation when this information was gathered for the instance.

    

    InstanceId -> (string)

      

      The ID of the managed instance the high-level patch compliance information was collected for.

      

      

    PatchGroup -> (string)

      

      The name of the patch group the managed instance belongs to.

      

      

    BaselineId -> (string)

      

      The ID of the patch baseline used to patch the instance.

      

      

    SnapshotId -> (string)

      

      The ID of the patch baseline snapshot used during the patching operation when this compliance data was collected.

      

      

    OwnerInformation -> (string)

      

      Placeholder information, this field will always be empty in the current release of the service.

      

      

    InstalledCount -> (integer)

      

      The number of patches from the patch baseline that are installed on the instance.

      

      

    InstalledOtherCount -> (integer)

      

      The number of patches not specified in the patch baseline that are installed on the instance.

      

      

    MissingCount -> (integer)

      

      The number of patches from the patch baseline that are applicable for the instance but aren't currently installed.

      

      

    FailedCount -> (integer)

      

      The number of patches from the patch baseline that were attempted to be installed during the last patching operation, but failed to install.

      

      

    NotApplicableCount -> (integer)

      

      The number of patches from the patch baseline that aren't applicable for the instance and hence aren't installed on the instance.

      

      

    OperationStartTime -> (timestamp)

      

      The time the most recent patching operation was started on the instance.

      

      

    OperationEndTime -> (timestamp)

      

      The time the most recent patching operation completed on the instance.

      

      

    Operation -> (string)

      

      The type of patching operation that was performed: SCAN (assess patch compliance state) or INSTALL (install missing patches).

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

