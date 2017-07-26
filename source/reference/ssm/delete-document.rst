[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm delete-document:


***************
delete-document
***************



===========
Description
===========



Deletes the Systems Manager document and all instance associations to the document.

 

Before you delete the document, we recommend that you use  delete-association to disassociate all instances that are associated with the document.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DeleteDocument>`_


========
Synopsis
========

::

    delete-document
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the document.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a document**

This example deletes a document. There is no output if the command succeeds.

Command::

  aws ssm delete-document --name "Config_2"


======
Output
======

