[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-client-certificate:


**********************
get-client-certificate
**********************



===========
Description
===========



Gets information about the current  ClientCertificate resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetClientCertificate>`_


========
Synopsis
========

::

    get-client-certificate
  --client-certificate-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-certificate-id`` (string)


  The identifier of the  ClientCertificate resource to be described.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get a client certificate**

Command::

  aws apigateway get-client-certificate --client-certificate-id a1b2c3


======
Output
======

clientCertificateId -> (string)

  

  The identifier of the client certificate.

  

  

description -> (string)

  

  The description of the client certificate.

  

  

pemEncodedCertificate -> (string)

  

  The PEM-encoded public key of the client certificate, which can be used to configure certificate authentication in the integration endpoint .

  

  

createdDate -> (timestamp)

  

  The timestamp when the client certificate was created.

  

  

expirationDate -> (timestamp)

  

  The timestamp when the client certificate will expire.

  

  

