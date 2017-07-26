[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` . :ref:`wait <cli:aws ses wait>` ]

.. _cli:aws ses wait identity-exists:


***************
identity-exists
***************



===========
Description
===========

Wait until JMESPath query VerificationAttributes.*.VerificationStatus returns Success for all elements when polling with ``get-identity-verification-attributes``. It will poll every 3 seconds until a successful state has been reached. This will exit with a return code of 255 after 20 failed checks.

========
Synopsis
========

::

    identity-exists
  --identities <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identities`` (list)


  A list of identities.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None