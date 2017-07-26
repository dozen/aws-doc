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



========
Synopsis
========

::

    create-branch
  --repository-name <value>
  --branch-name <value>
  --commit-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository in which you want to create the new branch.

  

``--branch-name`` (string)


  The name of the new branch to create.

  

``--commit-id`` (string)


  The ID of the commit to point the new branch to.

   

  .. note::

    If this commit ID is not specified, the new branch will point to the commit that is pointed to by the repository's default branch.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a branch**

This example creates a branch in an AWS CoceCommit repository. This command produces output only if there are errors.

Command::

  aws codecommit create-branch --repository-name MyDemoRepo --branch-name MyNewBranch --commit-id 317f8570EXAMPLE

Output::

  None.

======
Output
======

None