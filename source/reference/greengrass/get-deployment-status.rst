[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass get-deployment-status:


*********************
get-deployment-status
*********************



===========
Description
===========

Returns the status of a deployment.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/GetDeploymentStatus>`_


========
Synopsis
========

::

    get-deployment-status
  --deployment-id <value>
  --group-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--deployment-id`` (string)
the deployment Id

``--group-id`` (string)
The unique Id of the AWS Greengrass Group

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DeploymentStatus -> (string)

  Status of the deployment.

  

ErrorMessage -> (string)

  Error Message

  

UpdatedAt -> (string)

  Last time the deployment status was updated.

  

