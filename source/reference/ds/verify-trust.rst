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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/VerifyTrust>`_


========
Synopsis
========

::

    verify-trust
  --trust-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--trust-id`` (string)


  The unique Trust ID of the trust relationship to verify.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TrustId -> (string)

  

  The unique Trust ID of the trust relationship that was verified.

  

  

