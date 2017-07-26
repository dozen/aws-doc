[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` . :ref:`wait <cli:aws cloudformation wait>` ]

.. _cli:aws cloudformation wait change-set-create-complete:


**************************
change-set-create-complete
**************************



===========
Description
===========

Wait until change set status is CREATE_COMPLETE. It will poll every 30 seconds until a successful state has been reached. This will exit with a return code of 255 after 120 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DescribeChangeSet>`_


========
Synopsis
========

::

    change-set-create-complete
  --change-set-name <value>
  [--stack-name <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--change-set-name`` (string)


  The name or Amazon Resource Name (ARN) of the change set that you want to describe.

  

``--stack-name`` (string)


  If you specified the name of a change set, specify the stack name or ID (ARN) of the change set you want to describe.

  

``--next-token`` (string)


  A string (provided by the  describe-change-set response output) that identifies the next page of information that you want to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None