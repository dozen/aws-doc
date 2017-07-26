[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr get-login:


*********
get-login
*********



===========
Description
===========

Log in to an Amazon ECR registry.

This command retrieves a token that is valid for a specified registry for 12
hours, and then it prints a ``docker login`` command with that authorization
token. You can execute the printed command to log in to your registry with
Docker. After you have logged in to an Amazon ECR registry with this command,
you can use the Docker CLI to push and pull images from that registry until the
token expires.

.. note::

    This command writes displays ``docker login`` commands to stdout with
    authentication credentials. Your credentials could be visible by other
    users on your system in a process list display or a command history. If you
    are not on a secure system, you should consider this risk and login
    interactively. For more information, see ``get-authorization-token``.




========
Synopsis
========

::

    get-login
  [--registry-ids <value> [<value>...]]
  [--include-email | --no-include-email]




=======
Options
=======

``--registry-ids`` (string)
A list of AWS account IDs that correspond to the Amazon ECR registries that you want to log in to.

``--include-email`` | ``--no-include-email`` (boolean)
Specify if the '-e' flag should be included in the 'docker login' command. The '-e' option has been deprecated and is removed in docker version 17.06 and later. You must specify --no-include-email if you're using docker version 17.06 or later. The default behavior is to include the '-e' flag in the 'docker login' output.



========
Examples
========

**To retrieve a Docker login command to your default registry**

This example prints a command that you can use to log in to your default Amazon
ECR registry.

Command::

  aws ecr get-login

Output::

  docker login -u AWS -p <password> -e none https://<aws_account_id>.dkr.ecr.<region>.amazonaws.com

**To log in to another account's registry**

This example prints one or more commands that you can use to log in to
Amazon ECR registries associated with other accounts.

Command::

  aws ecr get-login --registry-ids 012345678910 023456789012

Output::

  docker login -u <username> -p <token-1> -e none <endpoint-1>
  docker login -u <username> -p <token-2> -e none <endpoint-2>
