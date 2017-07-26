[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy delete-deployment-config:


************************
delete-deployment-config
************************



===========
Description
===========



Deletes a deployment configuration.

 

.. note::

  A deployment configuration cannot be deleted if it is currently in use. Also, predefined configurations cannot be deleted.



========
Synopsis
========

::

    delete-deployment-config
  --deployment-config-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--deployment-config-name`` (string)


  The name of an existing deployment configuration associated with the applicable IAM user or AWS account.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a deployment configuration**

This example deletes a custom deployment configuration that is associated with the user's AWS account.

Command::

  aws deploy delete-deployment-config --deployment-config-name ThreeQuartersHealthy

Output::

  None.

======
Output
======

None