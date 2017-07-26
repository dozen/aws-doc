[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot attach-principal-policy:


***********************
attach-principal-policy
***********************



===========
Description
===========



Attaches the specified policy to the specified principal (certificate or other credential).



========
Synopsis
========

::

    attach-principal-policy
  --policy-name <value>
  --principal <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-name`` (string)


  The policy name.

  

``--principal`` (string)


  The principal which can be a certificate ARN (as returned from the CreateCertificate operation) or a Cognito ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None