[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-flow-logs:


****************
delete-flow-logs
****************



===========
Description
===========



Deletes one or more flow logs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DeleteFlowLogs>`_


========
Synopsis
========

::

    delete-flow-logs
  --flow-log-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--flow-log-ids`` (list)


  One or more flow log IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    

  

