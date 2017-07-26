[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit create-repository:


*****************
create-repository
*****************



===========
Description
===========



Creates a new, empty repository.



========
Synopsis
========

::

    create-repository
  --repository-name <value>
  [--repository-description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--repository-name`` (string)


  The name of the new repository to be created.

   

  .. note::

    The repository name must be unique across the calling AWS account. In addition, repository names are restricted to alphanumeric characters. The suffix ".git" is prohibited.

  

``--repository-description`` (string)


  A comment or description about the new repository.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a repository**

This example creates a repository and associates it with the user's AWS account.

Command::

  aws codecommit create-repository --repository-name MyDemoRepo --repository-description "My demonstration repository"

Output::

  {
      "repositoryMetadata": {
          "repositoryName": "MyDemoRepo",
		  "cloneUrlSsh": "ssh://git-codecommit.us-east-1.amazonaws.com/v1/repos/MyDemoRepo",
		  "lastModifiedDate": 1444766838.027,
          "repositoryDescription": "My demonstration repository",
		  "cloneUrlHttp": "https://git-codecommit.us-east-1.amazonaws.com/v1/repos/MyDemoRepo",
          "repositoryId": "f7579e13-b83e-4027-aaef-650c0EXAMPLE",
		  "Arn": "arn:aws:codecommit:us-east-1:111111111111EXAMPLE:MyDemoRepo",
          "accountId": "111111111111"
      }
  }

======
Output
======

repositoryMetadata -> (structure)

  

  Information about the newly created repository.

  

  accountId -> (string)

    

    The ID of the AWS account associated with the repository.

    

    

  repositoryId -> (string)

    

    The ID of the repository.

    

    

  repositoryName -> (string)

    

    The repository's name.

    

    

  repositoryDescription -> (string)

    

    A comment or description about the repository.

    

    

  defaultBranch -> (string)

    

    The repository's default branch name.

    

    

  lastModifiedDate -> (timestamp)

    

    The date and time the repository was last modified, in timestamp format.

    

    

  creationDate -> (timestamp)

    

    The date and time the repository was created, in timestamp format.

    

    

  cloneUrlHttp -> (string)

    

    The URL to use for cloning the repository over HTTPS.

    

    

  cloneUrlSsh -> (string)

    

    The URL to use for cloning the repository over SSH.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) of the repository.

    

    

  

