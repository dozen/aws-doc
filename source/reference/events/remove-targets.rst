[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events remove-targets:


**************
remove-targets
**************



===========
Description
===========



Removes target(s) from a rule so that when the rule is triggered, those targets will no longer be invoked.

 

 **Note:** When you make a change with this action, when the associated rule triggers, removed targets might still continue to be invoked. Please allow a short period of time for changes to take effect. 



========
Synopsis
========

::

    remove-targets
  --rule <value>
  --ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rule`` (string)


  The name of the rule you want to remove targets from.

  

``--ids`` (list)


  The list of target IDs to remove from the rule.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FailedEntryCount -> (integer)

  

  The number of failed entries.

  

  

FailedEntries -> (list)

  

  An array of failed target entries.

  

  (structure)

    

    The ID of the target requested to be removed from the rule by Amazon CloudWatch Events.

    

    TargetId -> (string)

      

      The ID of the target requested to be removed by Amazon CloudWatch Events.

      

      

    ErrorCode -> (string)

      

      The error code representing why the target removal failed on this entry.

      

      

    ErrorMessage -> (string)

      

      The error message explaining why the target removal failed on this entry.

      

      

    

  

