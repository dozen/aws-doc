[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm describe-luna-client:


********************
describe-luna-client
********************



===========
Description
===========



Retrieves information about an HSM client.



========
Synopsis
========

::

    describe-luna-client
  [--client-arn <value>]
  [--certificate-fingerprint <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--client-arn`` (string)


  The ARN of the client.

  

``--certificate-fingerprint`` (string)


  The certificate fingerprint.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ClientArn -> (string)

  

  The ARN of the client.

  

  

Certificate -> (string)

  

  The certificate installed on the HSMs used by this client.

  

  

CertificateFingerprint -> (string)

  

  The certificate fingerprint.

  

  

LastModifiedTimestamp -> (string)

  

  The date and time the client was last modified.

  

  

Label -> (string)

  

  The label of the client.

  

  

