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

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/UpdateDefaultBranch>`_


========
Synopsis
========

::

    update-default-branch
  --repository-name <value>
  --default-branch-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository to set or change the default branch for.

  

``--default-branch-name`` (string)


  The name of the branch to set as the default.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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