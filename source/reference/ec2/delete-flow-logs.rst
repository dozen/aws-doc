[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-flow-logs:


****************
delete-flow-logs
****************



===========
Description
===========



Deletes one or more flow logs.



========
Synopsis
========

::

    delete-flow-logs
  --flow-log-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--flow-log-ids`` (list)


  One or more flow log IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a flow log**

This example deletes flow log ``fl-1a2b3c4d``.

Command::

  aws ec2 delete-flow-logs --flow-log-id fl-1a2b3c4d

Output::

  {
    "Unsuccessful": []
  }

======
Output
======

Unsuccessful -> (list)

  

  Information about the flow logs that could not be deleted successfully.

  

  (structure)

    

    Information about items that were not successfully processed in a batch call.

    

    Error -> (structure)

      

      Information about the error.

      

      Code -> (string)

        

        The error code.

        

        

      Message -> (string)

        

        The error message accompanying the error code.

        

        

      

    ResourceId -> (string)

      

      The ID of the resource.

      

      

    

  

