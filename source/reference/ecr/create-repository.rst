[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr create-repository:


*****************
create-repository
*****************



===========
Description
===========



Creates an image repository.



========
Synopsis
========

::

    create-repository
  --repository-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--repository-name`` (string)


  The name to use for the repository. The repository name may be specified on its own (such as ``nginx-web-app`` ) or it can be prepended with a namespace to group the repository into a category (such as ``project-a/nginx-web-app`` ).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a repository**

This example creates a repository called ``nginx-web-app`` inside the
``project-a`` namespace in the default registry for an account.

Command::

  aws ecr create-repository --repository-name project-a/nginx-web-app

Output::

  {
      "repository": {
          "registryId": "<aws_account_id>",
          "repositoryName": "project-a/nginx-web-app",
          "repositoryArn": "arn:aws:ecr:us-west-2:<aws_account_id>:repository/project-a/nginx-web-app"
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

    

    

  

