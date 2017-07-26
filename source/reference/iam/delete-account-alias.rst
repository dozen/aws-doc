[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-account-alias:


********************
delete-account-alias
********************



===========
Description
===========



Deletes the specified AWS account alias. For information about using an AWS account alias, see `Using an Alias for Your AWS Account ID`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    delete-account-alias
  --account-alias <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-alias`` (string)


  The name of the account alias to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

.. _Using an Alias for Your AWS Account ID: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html
