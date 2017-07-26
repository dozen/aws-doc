[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm delete-association:


******************
delete-association
******************



===========
Description
===========



Disassociates the specified Systems Manager document from the specified instance.

 

When you disassociate a document from an instance, it does not change the configuration of the instance. To change the configuration state of an instance after you disassociate a document, you must create a new document with the desired configuration and associate it with the instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DeleteAssociation>`_


========
Synopsis
========

::

    delete-association
  [--name <value>]
  [--instance-id <value>]
  [--association-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the Systems Manager document.

  

``--instance-id`` (string)


  The ID of the instance.

  

``--association-id`` (string)


  The association ID that you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an association**

This example deletes the association between an instance and a document. There is no output if the command succeeds.

Command::

  aws ssm delete-association --instance-id "i-0cb2b964d3e14fd9f" --name "AWS-UpdateSSMAgent"


======
Output
======

