[ :ref:`aws <cli:aws>` . :ref:`sts <cli:aws sts>` ]

.. _cli:aws sts get-caller-identity:


*******************
get-caller-identity
*******************



===========
Description
===========



Returns details about the IAM identity whose credentials are used to call the API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sts-2011-06-15/GetCallerIdentity>`_


========
Synopsis
========

::

    get-caller-identity
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

UserId -> (string)

  

  The unique identifier of the calling entity. The exact value depends on the type of entity making the call. The values returned are those listed in the **aws:userid** column in the `Principal table <http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_variables.html#principaltable>`_ found on the **Policy Variables** reference page in the *IAM User Guide* .

  

  

Account -> (string)

  

  The AWS account ID number of the account that owns or contains the calling entity.

  

  

Arn -> (string)

  

  The AWS ARN associated with the calling entity.

  

  

