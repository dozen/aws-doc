[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit batch-get-repositories:


**********************
batch-get-repositories
**********************



===========
Description
===========



Gets information about one or more repositories.

 

.. note::

  

  The description field for a repository accepts all HTML characters and all valid Unicode characters. Applications that do not HTML-encode the description and display it in a web page could expose users to potentially malicious code. Make sure that you HTML-encode the description field in any application that uses this API to display the repository description on a web page.

  



========
Synopsis
========

::

    batch-get-repositories
  --repository-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--repository-names`` (list)


  The names of the repositories to get information about.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view details about multiple repositories**

This example shows details about multiple AWS CodeCommit repositories.

Command::

  aws codecommit batch-get-repositories --repository-names MyDemoRepo MyOtherDemoRepo

Output::

  {
        "repositories": [
             {
                "creationDate": 1429203623.625,
                "defaultBranch": "master",
                "repositoryName": "MyDemoRepo",
                "cloneUrlSsh": "ssh://ssh://git-codecommit.us-east-1.amazonaws.com/v1/repos//v1/repos/MyDemoRepo",
                "lastModifiedDate": 1430783812.0869999,
                "repositoryDescription": "My demonstration repository",
                "cloneUrlHttp": "https://codecommit.us-east-1.amazonaws.com/v1/repos/MyDemoRepo",
                "repositoryId": "f7579e13-b83e-4027-aaef-650c0EXAMPLE",
                "Arn": "arn:aws:codecommit:us-east-1:111111111111EXAMPLE:MyDemoRepo",
                "accountId": "111111111111"
            },
            {
                "creationDate": 1429203623.627,
                "defaultBranch": "master",
                "repositoryName": "MyOtherDemoRepo",
                "cloneUrlSsh": "ssh://ssh://git-codecommit.us-east-1.amazonaws.com/v1/repos//v1/repos/MyOtherDemoRepo",
                "lastModifiedDate": 1430783812.0889999,
                "repositoryDescription": "My other demonstration repository",
                "cloneUrlHttp": "https://codecommit.us-east-1.amazonaws.com/v1/repos/MyOtherDemoRepo",
                "repositoryId": "cfc29ac4-b0cb-44dc-9990-f6f51EXAMPLE",
                "Arn": "arn:aws:codecommit:us-east-1:111111111111EXAMPLE:MyOtherDemoRepo",
                "accountId": "111111111111"
            }
        ],
        "repositoriesNotFound": []
  }

======
Output
======

repositories -> (list)

  

  A list of repositories returned by the batch get repositories operation.

  

  (structure)

    

    Information about a repository.

    

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

      

      

    

  

repositoriesNotFound -> (list)

  

  Returns a list of repository names for which information could not be found.

  

  (string)

    Repository name is restricted to alphanumeric characters (a-z, A-Z, 0-9), ".", "_", and "-". Additionally, the suffix ".git" is prohibited in a repository name.

    

  

