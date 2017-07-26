[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm modify-hapg:


***********
modify-hapg
***********



===========
Description
===========



Modifies an existing high-availability partition group.



========
Synopsis
========

::

    modify-hapg
  --hapg-arn <value>
  [--label <value>]
  [--partition-serial-list <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

HapgArn -> (string)

  

  The ARN of the high-availability partition group.

  

  

