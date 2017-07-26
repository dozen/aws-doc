[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass list-deployments:


****************
list-deployments
****************



===========
Description
===========

Returns a history of deployments for the group.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/ListDeployments>`_


========
Synopsis
========

::

    list-deployments
  --group-id <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--group-id`` (string)
The unique Id of the AWS Greengrass Group

``--max-results`` (string)
Specifies the maximum number of list results to be returned in this page

``--next-token`` (string)
Specifies the pagination token used when iterating through a paginated request

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Deployments -> (list)

  Information on deployments

  (structure)

    Information on the deployment

    CreatedAt -> (string)

      Timestamp when the deployment was created.

      

    DeploymentArn -> (string)

      Arn of the deployment.

      

    DeploymentId -> (string)

      Id of the deployment.

      

    GroupArn -> (string)

      Arn of the group for this deployment.

      

    

  

NextToken -> (string)

  The token for the next set of results, or ''null'' if there are no additional results.

  

