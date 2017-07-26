[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit get-branch:


**********
get-branch
**********



===========
Description
===========



Retrieves information about a repository branch, including its name and the last commit ID.



========
Synopsis
========

::

    get-branch
  [--repository-name <value>]
  [--branch-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--repository-name`` (string)
Repository name is restricted to alphanumeric characters (a-z, A-Z, 0-9), ".", "_", and "-". Additionally, the suffix ".git" is prohibited in a repository name.

``--branch-name`` (string)


  The name of the branch for which you want to retrieve information.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about a branch**

This example gets information about a branch in an AWS CoceCommit repository.

Command::

  aws codecommit get-branch --repository-name MyDemoRepo --branch-name MyNewBranch

Output::

  {
    "BranchInfo": {
          "commitID": "317f8570EXAMPLE",
		  "branchName": "MyNewBranch"
    }
  }

======
Output
======

branch -> (structure)

  

  The name of the branch.

  

  branchName -> (string)

    

    The name of the branch.

    

    

  commitId -> (string)

    

    The ID of the last commit made to the branch.

    

    

  

