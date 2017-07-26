[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm modify-hapg:


***********
modify-hapg
***********



===========
Description
===========



Modifies an existing high-availability partition group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/ModifyHapg>`_


========
Synopsis
========

::

    modify-hapg
  --hapg-arn <value>
  [--label <value>]
  [--partition-serial-list <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hapg-arn`` (string)


  The ARN of the high-availability partition group to modify.

  

``--label`` (string)


  The new label for the high-availability partition group.

  

``--partition-serial-list`` (list)


  The list of partition serial numbers to make members of the high-availability partition group.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HapgArn -> (string)

  

  The ARN of the high-availability partition group.

  

  

