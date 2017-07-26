[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` . :ref:`wait <cli:aws ses wait>` ]

.. _cli:aws ses wait identity-exists:


***************
identity-exists
***************



===========
Description
===========

Wait until JMESPath query VerificationAttributes.*.VerificationStatus returns Success for all elements when polling with ``get-identity-verification-attributes``. It will poll every 3 seconds until a successful state has been reached. This will exit with a return code of 255 after 20 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/GetIdentityVerificationAttributes>`_


========
Synopsis
========

::

    identity-exists
  --identities <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identities`` (list)


  A list of identities.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None