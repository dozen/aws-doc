[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-domain-names:


****************
get-domain-names
****************



===========
Description
===========



Represents a collection of  DomainName resources.



``get-domain-names`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``items``


========
Synopsis
========

::

    get-domain-names
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

position -> (string)

  

  

items -> (list)

  

  The current page of any  DomainName resources in the collection of  DomainName resources.

  

  (structure)

    

    Represents a domain name that is contained in a simpler, more intuitive URL that can be called.

    

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
