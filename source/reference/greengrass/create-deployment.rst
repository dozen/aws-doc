[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass create-deployment:


*****************
create-deployment
*****************



===========
Description
===========

Creates a deployment.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/CreateDeployment>`_


========
Synopsis
========

::

    create-deployment
  [--amzn-client-token <value>]
  [--deployment-id <value>]
  [--deployment-type <value>]
  --group-id <value>
  [--group-version-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--amzn-client-token`` (string)
The client token used to request idempotent operations.

``--deployment-id`` (string)
Id of the deployment if you wish to redeploy a previous deployment.

``--deployment-type`` (string)
Type of deployment

  Possible values:

  
  *   ``NewDeployment``

  
  *   ``Redeployment``

  

  

``--group-id`` (string)
The unique Id of the AWS Greengrass Group

``--group-version-id`` (string)
Group Version you wish to deploy.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DeploymentArn -> (string)

  Arn of the deployment.

  

DeploymentId -> (string)

  Id of the deployment.

  

