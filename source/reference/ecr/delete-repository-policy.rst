[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr delete-repository-policy:


************************
delete-repository-policy
************************



===========
Description
===========



Deletes the repository policy from a specified repository.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/DeleteRepositoryPolicy>`_


========
Synopsis
========

::

    delete-repository-policy
  [--registry-id <value>]
  --repository-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the repository policy to delete. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository that is associated with the repository policy to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

registryId -> (string)

  

  The registry ID associated with the request.

  

  

repositoryName -> (string)

  

  The repository name associated with the request.

  

  

policyText -> (string)

  

  The JSON repository policy that was deleted from the repository.

  

  

