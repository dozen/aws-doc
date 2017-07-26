[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr delete-repository:


*****************
delete-repository
*****************



===========
Description
===========



Deletes an existing image repository. If a repository contains images, you must use the ``force`` option to delete it.



========
Synopsis
========

::

    delete-repository
  [--registry-id <value>]
  --repository-name <value>
  [--force | --no-force]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the repository to delete. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository to delete.

  

``--force`` | ``--no-force`` (boolean)


  Force the deletion of the repository if it contains images.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a repository**

This example command force deletes a repository named ``ubuntu`` in the default
registry for an account. The ``--force`` flag is required if the repository
contains images.

Command::

  aws ecr delete-repository --force --repository-name ubuntu

Output::

  {
      "repository": {
          "registryId": "<aws_account_id>",
          "repositoryName": "ubuntu",
          "repositoryArn": "arn:aws:ecr:us-west-2:<aws_account_id>:repository/ubuntu"
      }
  }


======
Output
======

repository -> (structure)

  

  Object representing a repository.

  

  repositoryArn -> (string)

    

    The Amazon Resource Name (ARN) that identifies the repository. The ARN contains the ``arn:aws:ecr`` namespace, followed by the region of the repository, the AWS account ID of the repository owner, the repository namespace, and then the repository name. For example, ``arn:aws:ecr:region:012345678910:repository/test`` .

    

    

  registryId -> (string)

    

    The AWS account ID associated with the registry that contains the repository.

    

    

  repositoryName -> (string)

    

    The name of the repository.

    

    

  

