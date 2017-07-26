[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-domain-name:


******************
create-domain-name
******************



===========
Description
===========



Creates a new domain name.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/CreateDomainName>`_


========
Synopsis
========

::

    create-domain-name
  --domain-name <value>
  [--certificate-name <value>]
  [--certificate-body <value>]
  [--certificate-private-key <value>]
  [--certificate-chain <value>]
  [--certificate-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  (Required) The name of the  DomainName resource.

  

``--certificate-name`` (string)


  The user-friendly name of the certificate.

  

``--certificate-body`` (string)


  [Deprecated] The body of the server certificate provided by your certificate authority.

  

``--certificate-private-key`` (string)


  [Deprecated] Your certificate's private key.

  

``--certificate-chain`` (string)


  [Deprecated] The intermediate certificates and optionally the root certificate, one after the other without any blank lines. If you include the root certificate, your certificate chain must start with intermediate certificates and end with the root certificate. Use the intermediate certificates that were provided by your certificate authority. Do not include any intermediaries that are not in the chain of trust path.

  

``--certificate-arn`` (string)


  The reference to an AWS-managed certificate. AWS Certificate Manager is the only supported source.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create the custom domain name**

Command::

  aws apigateway create-domain-name --domain-name 'my.domain.tld' --certificate-name 'my.domain.tld cert' --certificate-body '<cert here>' --certificate-private-key '<cert key here>' --certificate-chain '<cert chain here>'


======
Output
======

domainName -> (string)

  

  The name of the  DomainName resource.

  

  

certificateName -> (string)

  

  The name of the certificate.

  

  

certificateArn -> (string)

  

  The reference to an AWS-managed certificate. AWS Certificate Manager is the only supported source.

  

  

certificateUploadDate -> (timestamp)

  

  The timestamp when the certificate was uploaded.

  

  

distributionDomainName -> (string)

  

  The domain name of the Amazon CloudFront distribution. For more information, see the `Amazon CloudFront documentation <http://aws.amazon.com/documentation/cloudfront/>`_ .

  

  

