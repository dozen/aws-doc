[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit list-repositories:


*****************
list-repositories
*****************



===========
Description
===========



Gets information about one or more repositories.



========
Synopsis
========

::

    list-repositories
  [--next-token <value>]
  [--sort-by <value>]
  [--order <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--next-token`` (string)


  An enumeration token that allows the operation to batch the results of the operation. Batch sizes are 1,000 for list repository operations. When the client sends the token back to AWS CodeCommit, another page of 1,000 records is retrieved.

  

``--sort-by`` (string)


  The criteria used to sort the results of a list repositories operation.

  

  Possible values:

  
  *   ``repositoryName``

  
  *   ``lastModifiedDate``

  

  

``--order`` (string)


  The order in which to sort the results of a list repositories operation.

  

  Possible values:

  
  *   ``ascending``

  
  *   ``descending``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view a list of repositories**

This example lists all AWS CodeCommit repositories associated with the user's AWS account.

Command::

  aws codecommit list-repositories

Output::

  {
    "repositories": [
        {
           "repositoryName": "MyDemoRepo"
           "repositoryId": "f7579e13-b83e-4027-aaef-650c0EXAMPLE",
        },
        {
           "repositoryName": "MyOtherDemoRepo"
           "repositoryId": "cfc29ac4-b0cb-44dc-9990-f6f51EXAMPLE"
        }
    ]
  }

======
Output
======

repositories -> (list)

  

  Lists the repositories called by the list repositories operation.

  

  (structure)

    

    Information about a repository name and ID.

    

    repositoryName -> (string)

      Repository name is restricted to alphanumeric characters (a-z, A-Z, 0-9), ".", "_", and "-". Additionally, the suffix ".git" is prohibited in a repository name.

      

    repositoryId -> (string)

      

      The ID associated with the repository name.

      

      

    

  

nextToken -> (string)

  

  An enumeration token that allows the operation to batch the results of the operation. Batch sizes are 1,000 for list repository operations. When the client sends the token back to AWS CodeCommit, another page of 1,000 records is retrieved.

  

  

