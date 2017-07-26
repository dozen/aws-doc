[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-account-alias:


********************
delete-account-alias
********************



===========
Description
===========



Deletes the specified AWS account alias. For information about using an AWS account alias, see `Using an Alias for Your AWS Account ID <http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/DeleteAccountAlias>`_


========
Synopsis
========

::

    delete-account-alias
  --account-alias <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-alias`` (string)


  The name of the account alias to delete.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of lowercase letters, digits, and dashes. You cannot start or finish with a dash, nor can you have two dashes in a row.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an account alias**

The following ``delete-account-alias`` command removes the alias ``mycompany`` for the current account::

  aws iam delete-account-alias --account-alias mycompany

For more information, see `Using an Alias for Your AWS Account ID`_ in the *Using IAM* guide.

.. _`Using an Alias for Your AWS Account ID`: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html


======
Output
======

None