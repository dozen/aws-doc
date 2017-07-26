[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr delete-repository-policy:


************************
delete-repository-policy
************************



===========
Description
===========



Deletes the repository policy from a specified repository.



========
Synopsis
========

::

    delete-repository-policy
  [--registry-id <value>]
  --repository-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the repository policy to delete. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository that is associated with the repository policy to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

registryId -> (string)

  

  The registry ID associated with the request.

  

  

repositoryName -> (string)

  

  The repository name associated with the request.

  

  

policyText -> (string)

  

  The JSON repository policy that was deleted from the repository.

  

  

