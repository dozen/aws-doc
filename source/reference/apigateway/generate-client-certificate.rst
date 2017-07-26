[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway generate-client-certificate:


***************************
generate-client-certificate
***************************



===========
Description
===========



Generates a  ClientCertificate resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GenerateClientCertificate>`_


========
Synopsis
========

::

    generate-client-certificate
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--description`` (string)


  The description of the  ClientCertificate .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a Client-Side SSL Certificate**

Command::

  aws apigateway generate-client-certificate --description 'My First Client Certificate'


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

  

  

