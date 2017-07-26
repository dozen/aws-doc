[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit update-repository-name:


**********************
update-repository-name
**********************



===========
Description
===========



Renames a repository.



========
Synopsis
========

::

    update-repository-name
  --old-name <value>
  --new-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--old-name`` (string)
Repository name is restricted to alphanumeric characters (a-z, A-Z, 0-9), ".", "_", and "-". Additionally, the suffix ".git" is prohibited in a repository name.

``--new-name`` (string)
Repository name is restricted to alphanumeric characters (a-z, A-Z, 0-9), ".", "_", and "-". Additionally, the suffix ".git" is prohibited in a repository name.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To change the name of a repository**

This example changes the name of an AWS CodeCommit repository. This command produces output only if there are errors. Changing the name of the AWS CodeCommit repository will change the SSH and HTTPS URLs that users need to connect to the repository. Users will not be able to connect to this repository until they update their connection settings. Also, because the repository's ARN will change, changing the repository name will invalidate any IAM user policies that rely on this repository's ARN.

Command::

  aws codecommit update-repository-name --old-name MyDemoRepo --new-name MyRenamedDemoRepo

Output::

  None.

======
Output
======

None