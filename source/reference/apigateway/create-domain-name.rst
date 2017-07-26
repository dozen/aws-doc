[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-domain-name:


******************
create-domain-name
******************



===========
Description
===========



Creates a new domain name.



========
Synopsis
========

::

    create-domain-name
  --domain-name <value>
  --certificate-name <value>
  --certificate-body <value>
  --certificate-private-key <value>
  --certificate-chain <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The name of the  DomainName resource.

  

``--certificate-name`` (string)


  The name of the certificate.

  

``--certificate-body`` (string)


  The body of the server certificate provided by your certificate authority.

  

``--certificate-private-key`` (string)


  Your certificate's private key.

  

``--certificate-chain`` (string)


  The intermediate certificates and optionally the root certificate, one after the other without any blank lines. If you include the root certificate, your certificate chain must start with intermediate certificates and end with the root certificate. Use the intermediate certificates that were provided by your certificate authority. Do not include any intermediaries that are not in the chain of trust path.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

domainName -> (string)

  

  The name of the  DomainName resource.

  

  

certificateName -> (string)

  

  The name of the certificate.

  

  

certificateUploadDate -> (timestamp)

  

  The date when the certificate was uploaded, in `ISO 8601 format`_ .

  

  

distributionDomainName -> (string)

  

  The domain name of the Amazon CloudFront distribution. For more information, see the `Amazon CloudFront documentation`_ .

  

  



.. _Amazon CloudFront documentation: http://aws.amazon.com/documentation/cloudfront/
.. _ISO 8601 format: http://www.iso.org/iso/home/standards/iso8601.htm
