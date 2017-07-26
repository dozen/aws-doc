[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass get-group-certificate-configuration:


***********************************
get-group-certificate-configuration
***********************************



===========
Description
===========

Retrieves the current configuration for the CA used by the group.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/GetGroupCertificateConfiguration>`_


========
Synopsis
========

::

    get-group-certificate-configuration
  --group-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--group-id`` (string)
The unique Id of the AWS Greengrass Group

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CertificateAuthorityExpiryInMilliseconds -> (string)

  Amount of time when the certificate authority expires in milliseconds.

  

CertificateExpiryInMilliseconds -> (string)

  Amount of time when the certificate expires in milliseconds.

  

GroupId -> (string)

  Id of the group the certificate configuration belongs to.

  

