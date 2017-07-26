[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-account-alias:


********************
create-account-alias
********************



===========
Description
===========



Creates an alias for your AWS account. For information about using an AWS account alias, see `Using an Alias for Your AWS Account ID <http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/CreateAccountAlias>`_


========
Synopsis
========

::

    create-account-alias
  --account-alias <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-alias`` (string)


  The account alias to create.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of lowercase letters, digits, and dashes. You cannot start or finish with a dash, nor can you have two dashes in a row.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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