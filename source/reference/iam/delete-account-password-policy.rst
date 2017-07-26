[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-account-password-policy:


******************************
delete-account-password-policy
******************************



===========
Description
===========



Deletes the password policy for the AWS account. There are no parameters.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/DeleteAccountPasswordPolicy>`_


========
Synopsis
========

::

    delete-account-password-policy
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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