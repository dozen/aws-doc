[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit delete-repository:


*****************
delete-repository
*****************



===========
Description
===========



Deletes a repository. If a specified repository was already deleted, a null repository ID will be returned.

 

.. warning::

  Deleting a repository also deletes all associated objects and metadata. After a repository is deleted, all future push calls to the deleted repository will fail.



========
Synopsis
========

::

    delete-repository
  --repository-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a repository**

This example shows how to delete an AWS CodeCommit repository.

Command::

  aws codecommit delete-repository --repository-name MyDemoRepo

Output::

  {
    "repositoryId": "f7579e13-b83e-4027-aaef-650c0EXAMPLE"
  }

======
Output
======

repositoryId -> (string)

  

  The ID of the repository that was deleted.

  

  

