[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-domain-name:


***************
get-domain-name
***************



===========
Description
===========



Represents a domain name that is contained in a simpler, more intuitive URL that can be called.



========
Synopsis
========

::

    get-domain-name
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The name of the  DomainName resource.

  

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