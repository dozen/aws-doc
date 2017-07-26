[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-instance-patch-states-for-patch-group:


**********************************************
describe-instance-patch-states-for-patch-group
**********************************************



===========
Description
===========



Retrieves the high-level patch state for the instances in the specified patch group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeInstancePatchStatesForPatchGroup>`_


========
Synopsis
========

::

    describe-instance-patch-states-for-patch-group
  --patch-group <value>
  [--filters <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--patch-group`` (string)


  The name of the patch group for which the patch state information should be retrieved.

  

``--filters`` (list)


  Each entry in the array is a structure containing:

   

  Key (string between 1 and 200 characters)

   

  Values (array containing a single string)

   

  Type (string "Equal", "NotEqual", "LessThan", "GreaterThan")

  



Shorthand Syntax::

    Key=string,Values=string,string,Type=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Values": ["string", ...],
      "Type": "Equal"|"NotEqual"|"LessThan"|"GreaterThan"
    }
    ...
  ]



``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--max-results`` (integer)


  The maximum number of patches to return (per page).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the instance states for a patch group**

This example gets the patch summary states per-instance for a patch group.

Command::

  aws ssm describe-instance-patch-states-for-patch-group --patch-group "Production"

Output::

  {
    "InstancePatchStates": [
	   {
         "OperationStartTime":1481259600.0,
         "FailedCount":0,
         "InstanceId":"i-08ee91c0b17045407",
         "OwnerInformation":"",
         "NotApplicableCount":2077,
         "OperationEndTime":1481259757.0,
         "PatchGroup":"Production",
         "InstalledOtherCount":186,
         "MissingCount":7,
         "SnapshotId":"b0e65479-79be-4288-9f88-81c96bc3ed5e",
         "Operation":"Scan",
         "InstalledCount":72
       },
       {
         "OperationStartTime":1481259602.0,
         "FailedCount":0,
         "InstanceId":"i-0fff3aab684d01b23",
         "OwnerInformation":"",
         "NotApplicableCount":2692,
         "OperationEndTime":1481259613.0,
         "PatchGroup":"Production",
         "InstalledOtherCount":3,
         "MissingCount":1,
         "SnapshotId":"b0e65479-79be-4288-9f88-81c96bc3ed5e",
         "Operation":"Scan",
         "InstalledCount":1
       },
	   ...
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

  

  

