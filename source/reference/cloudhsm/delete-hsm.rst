[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm delete-hsm:


**********
delete-hsm
**********



===========
Description
===========



Deletes an HSM. Once complete, this operation cannot be undone and your key material cannot be recovered.



========
Synopsis
========

::

    delete-hsm
  --hsm-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--hsm-arn`` (string)


  The ARN of the HSM to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Status -> (string)

  

  The status of the action.

  

  

