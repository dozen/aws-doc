[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events put-targets:


***********
put-targets
***********



===========
Description
===========



Adds target(s) to a rule. Updates the target(s) if they are already associated with the role. In other words, if there is already a target with the given target ID, then the target associated with that ID is updated.

 

 **Note:** When you make a change with this action, when the associated rule triggers, new or updated targets might not be immediately invoked. Please allow a short period of time for changes to take effect. 



========
Synopsis
========

::

    put-targets
  --rule <value>
  --targets <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rule`` (string)


  The name of the rule you want to add targets to.

  

``--targets`` (list)


  List of targets you want to update or add to the rule.

  



Shorthand Syntax::

    Id=string,Arn=string,Input=string,InputPath=string ...




JSON Syntax::

  [
    {
      "Id": "string",
      "Arn": "string",
      "Input": "string",
      "InputPath": "string"
    }
    ...
  ]



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

    

    A PutTargetsResult contains a list of PutTargetsResultEntry.

    

    TargetId -> (string)

      

      The ID of the target submitted to Amazon CloudWatch Events.

      

      

    ErrorCode -> (string)

      

      The error code representing why the target submission failed on this entry.

      

      

    ErrorMessage -> (string)

      

      The error message explaining why the target submission failed on this entry.

      

      

    

  

