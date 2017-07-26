[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm delete-association:


******************
delete-association
******************



===========
Description
===========



Disassociates the specified SSM document from the specified instance.

 

When you disassociate an SSM document from an instance, it does not change the configuration of the instance. To change the configuration state of an instance after you disassociate a document, you must create a new document with the desired configuration and associate it with the instance.



========
Synopsis
========

::

    delete-association
  --name <value>
  --instance-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the SSM document.

  

``--instance-id`` (string)


  The ID of the instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete an association**

This example deletes the association between instance ``i-bbcc3344`` and the configuration document ``Test_config``. If the command succeeds, no output is returned.

Command::

  aws ssm delete-association --instance-id i-bbcc3344 --name Test_config



======
Output
======

