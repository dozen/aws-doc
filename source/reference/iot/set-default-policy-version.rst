[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot set-default-policy-version:


**************************
set-default-policy-version
**************************



===========
Description
===========



Sets the specified version of the specified policy as the policy's default (operative) version. This action affects all certificates that the policy is attached to. To list the principals the policy is attached to, use the ListPrincipalPolicy API.



========
Synopsis
========

::

    set-default-policy-version
  --policy-name <value>
  --policy-version-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-name`` (string)


  The policy name.

  

``--policy-version-id`` (string)


  The policy version ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None