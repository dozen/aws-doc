[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm delete-document:


***************
delete-document
***************



===========
Description
===========



Deletes the SSM document and all instance associations to the document.

 

Before you delete the SSM document, we recommend that you use delete-association to disassociate all instances that are associated with the document.



========
Synopsis
========

::

    delete-document
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the SSM document.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a configuration document**

This example deletes the configuration document called ``Config_2``. If the command succeeds, no output is returned.

Command::

  aws ssm delete-document --name "Config_2"


======
Output
======

