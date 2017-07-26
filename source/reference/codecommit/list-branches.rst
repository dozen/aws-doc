[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit list-branches:


*************
list-branches
*************



===========
Description
===========



Gets information about one or more branches in a repository.



========
Synopsis
========

::

    list-branches
  --repository-name <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository that contains the branches.

  

``--next-token`` (string)


  An enumeration token that allows the operation to batch the results. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view a list of branch names**

This example lists all branch names in an AWS CoceCommit repository.

Command::

  aws codecommit list-branches --repository-name MyDemoRepo

Output::

  {
    "branches": [
        "MyNewBranch",
        "master"
    ]
  }

======
Output
======

branches -> (list)

  

  The list of branch names.

  

  (string)

    

    

  

nextToken -> (string)

  

  An enumeration token that returns the batch of the results. 

  

  

