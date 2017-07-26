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

   

  A deployment configuration cannot be deleted if it is currently in use. Predefined configurations cannot be deleted.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/DeleteDeploymentConfig>`_


========
Synopsis
========

::

    delete-deployment-config
  --deployment-config-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--deployment-config-name`` (string)


  The name of a deployment configuration associated with the applicable IAM user or AWS account.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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