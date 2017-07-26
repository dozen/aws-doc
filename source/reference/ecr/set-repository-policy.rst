[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr set-repository-policy:


*********************
set-repository-policy
*********************



===========
Description
===========



Applies a repository policy on a specified repository to control access permissions.



========
Synopsis
========

::

    set-repository-policy
  [--registry-id <value>]
  --repository-name <value>
  --policy-text <value>
  [--force | --no-force]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the repository. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository to receive the policy.

  

``--policy-text`` (string)


  The JSON repository policy text to apply to the repository.

  

``--force`` | ``--no-force`` (boolean)


  If the policy you are attempting to set on a repository policy would prevent you from setting another policy in the future, you must force the  set-repository-policy operation. This is intended to prevent accidental repository lock outs.

  

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

  

  The JSON repository policy text applied to the repository.

  

  

