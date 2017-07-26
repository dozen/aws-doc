[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit update-default-branch:


*********************
update-default-branch
*********************



===========
Description
===========



Sets or changes the default branch name for the specified repository.

 

.. note::

  If you use this operation to change the default branch name to the current default branch name, a success message is returned even though the default branch did not change.



========
Synopsis
========

::

    update-default-branch
  --repository-name <value>
  --default-branch-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository to set or change the default branch for.

  

``--default-branch-name`` (string)


  The name of the branch to set as the default.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To change the default branch for a repository**

This example changes the default branch for an AWS CodeCommit repository. This command produces output only if there are errors.

Command::

  aws codecommit update-default-branch --repository-name MyDemoRepo --default-branch-name MyNewBranch

Output::

  None.

======
Output
======

None