[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy deregister-on-premises-instance:


*******************************
deregister-on-premises-instance
*******************************



===========
Description
===========



Deregisters an on-premises instance.



========
Synopsis
========

::

    deregister-on-premises-instance
  --instance-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-name`` (string)


  The name of the on-premises instance to deregister.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To deregister an on-premises instance**

This example deregisters an on-premises instance with AWS CodeDeploy, but it does not delete the IAM user associated with the instance, nor does it disassociate in AWS CodeDeploy the on-premises instance tags from the instance. It also does not uninstall the AWS CodeDeploy Agent from the instance nor remove the on-premises configuration file from the instance.

Command::

  aws deploy deregister-on-premises-instance --instance-name AssetTag12010298EX

Output::

  This command produces no output.

======
Output
======

None