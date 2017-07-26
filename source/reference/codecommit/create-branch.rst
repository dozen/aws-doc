[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit create-branch:


*************
create-branch
*************



===========
Description
===========



Creates a new branch in a repository and points the branch to a commit.

 

.. note::

   

  Calling the create branch operation does not set a repository's default branch. To do this, call the update default branch operation.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/CreateBranch>`_


========
Synopsis
========

::

    create-branch
  --repository-name <value>
  --branch-name <value>
  --commit-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository in which you want to create the new branch.

  

``--branch-name`` (string)


  The name of the new branch to create.

  

``--commit-id`` (string)


  The ID of the commit to point the new branch to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a branch**

This example creates a branch in an AWS CodeCommit repository. This command produces output only if there are errors.

Command::

  aws codecommit create-branch --repository-name MyDemoRepo --branch-name MyNewBranch --commit-id 317f8570EXAMPLE

Output::

  None.


======
Output
======

None