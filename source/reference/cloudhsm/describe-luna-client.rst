[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm describe-luna-client:


********************
describe-luna-client
********************



===========
Description
===========



Retrieves information about an HSM client.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/DescribeLunaClient>`_


========
Synopsis
========

::

    describe-luna-client
  [--client-arn <value>]
  [--certificate-fingerprint <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-arn`` (string)


  The ARN of the client.

  

``--certificate-fingerprint`` (string)


  The certificate fingerprint.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

