[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit get-repository:


**************
get-repository
**************



===========
Description
===========



Gets information about a repository.

 

.. note::

  

  The description field for a repository accepts all HTML characters and all valid Unicode characters. Applications that do not HTML-encode the description and display it in a web page could expose users to potentially malicious code. Make sure that you HTML-encode the description field in any application that uses this API to display the repository description on a web page.

  



========
Synopsis
========

::

    get-repository
  --repository-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about a repository**

This example shows details about an AWS CodeCommit repository.

Command::

  aws codecommit get-repository --repository-name MyDemoRepo

Output::

  {
    "repositoryMetadata": {
            "creationDate": 1429203623.625,
            "defaultBranch": "master",
            "repositoryName": "MyDemoRepo",
            "cloneUrlSsh": "ssh://ssh://git-codecommit.us-east-1.amazonaws.com/v1/repos//v1/repos/MyDemoRepo",
            "lastModifiedDate": 1430783812.0869999,
            "repositoryDescription": "My demonstration repository",
            "cloneUrlHttp": "https://codecommit.us-east-1.amazonaws.com/v1/repos/MyDemoRepo",
            "repositoryId": "f7579e13-b83e-4027-aaef-650c0EXAMPLE",
            "Arn": "arn:aws:codecommit:us-east-1:80398EXAMPLE:MyDemoRepo
            "accountId": "111111111111"
        }
  }

======
Output
======

repositoryMetadata -> (structure)

  

  Information about the repository.

  

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

    

    

  

