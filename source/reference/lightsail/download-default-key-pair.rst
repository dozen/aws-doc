[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail download-default-key-pair:


*************************
download-default-key-pair
*************************



===========
Description
===========



Downloads the default SSH key pair from the user's account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/DownloadDefaultKeyPair>`_


========
Synopsis
========

::

    download-default-key-pair
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

publicKeyBase64 -> (string)

  

  A base64-encoded public key of the ``ssh-rsa`` type.

  

  

privateKeyBase64 -> (string)

  

  A base64-encoded RSA private key.

  

  

