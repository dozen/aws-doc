[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-account-alias:


********************
create-account-alias
********************



===========
Description
===========



Creates an alias for your AWS account. For information about using an AWS account alias, see `Using an Alias for Your AWS Account ID`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    create-account-alias
  --account-alias <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-alias`` (string)


  The account alias to create.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an account alias**

The following ``create-account-alias`` command creates the alias ``examplecorp`` for your AWS account::

  aws iam create-account-alias --account-alias examplecorp

For more information, see `Your AWS Account ID and Its Alias`_ in the *Using IAM* guide.

.. _`Your AWS Account ID and Its Alias`: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html


======
Output
======

None

.. _Using an Alias for Your AWS Account ID: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html
