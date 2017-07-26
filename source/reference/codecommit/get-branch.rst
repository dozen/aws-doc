[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit get-branch:


**********
get-branch
**********



===========
Description
===========



Returns information about a repository branch, including its name and the last commit ID.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/GetBranch>`_


========
Synopsis
========

::

    get-branch
  [--repository-name <value>]
  [--branch-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository that contains the branch for which you want to retrieve information.

  

``--branch-name`` (string)


  The name of the branch for which you want to retrieve information.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about a branch**

This example gets information about a branch in an AWS CodeCommit repository.

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

    

    

  

