[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms generate-random:


***************
generate-random
***************



===========
Description
===========



Returns a random byte string that is cryptographically secure.

 

For more information about entropy and random number generation, see the `AWS Key Management Service Cryptographic Details <https://d0.awsstatic.com/whitepapers/KMS-Cryptographic-Details.pdf>`_ whitepaper.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/GenerateRandom>`_


========
Synopsis
========

::

    generate-random
  [--number-of-bytes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--number-of-bytes`` (integer)


  The length of the byte string.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Plaintext -> (blob)

  

  The random byte string.

  

  

