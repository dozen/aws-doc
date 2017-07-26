[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-account-password-policy:


******************************
delete-account-password-policy
******************************



===========
Description
===========



Deletes the password policy for the AWS account.



========
Synopsis
========

::

    delete-account-password-policy
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete the current account password policy**

The following ``delete-account-password-policy`` command removes the password policy for the current account::

    aws iam delete-account-password-policy

For more information, see `Managing an IAM Password Policy`_ in the *Using IAM* guide.

.. _`Managing an IAM Password Policy`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingPasswordPolicies.html



======
Output
======

None