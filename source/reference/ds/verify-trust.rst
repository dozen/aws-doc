[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds verify-trust:


************
verify-trust
************



===========
Description
===========



AWS Directory Service for Microsoft Active Directory allows you to configure and verify trust relationships. 



This action verifies a trust relationship between your Microsoft AD in the AWS cloud and an external domain.



========
Synopsis
========

::

    verify-trust
  --trust-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--trust-id`` (string)
The unique Trust ID of the trust relationship to verify.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrustId -> (string)

  The unique Trust ID of the trust relationship that was verified.

  

