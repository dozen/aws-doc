[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr create-repository:


*****************
create-repository
*****************



===========
Description
===========



Creates an image repository.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/CreateRepository>`_


========
Synopsis
========

::

    create-repository
  --repository-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name to use for the repository. The repository name may be specified on its own (such as ``nginx-web-app`` ) or it can be prepended with a namespace to group the repository into a category (such as ``project-a/nginx-web-app`` ).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  The repository that was created.

  

  repositoryArn -> (string)

    

    The Amazon Resource Name (ARN) that identifies the repository. The ARN contains the ``arn:aws:ecr`` namespace, followed by the region of the repository, the AWS account ID of the repository owner, the repository namespace, and then the repository name. For example, ``arn:aws:ecr:region:012345678910:repository/test`` .

    

    

  registryId -> (string)

    

    The AWS account ID associated with the registry that contains the repository.

    

    

  repositoryName -> (string)

    

    The name of the repository.

    

    

  repositoryUri -> (string)

    

    The URI for the repository. You can use this URI for Docker ``push`` and ``pull`` operations.

    

    

  createdAt -> (timestamp)

    

    The date and time, in JavaScript date/time format, when the repository was created.

    

    

  

