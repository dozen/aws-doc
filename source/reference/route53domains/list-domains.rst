[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains list-domains:


************
list-domains
************



===========
Description
===========



This operation returns all the domain names registered with Amazon Route 53 for the current AWS account.



``list-domains`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Domains``


========
Synopsis
========

::

    list-domains
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Domains -> (list)

  

  A summary of domains.

   

  Type: Complex type containing a list of domain summaries.

   

  Children: ``AutoRenew`` , ``DomainName`` , ``Expiry`` , ``TransferLock`` 

  

  (structure)

    

    DomainName -> (string)

      

      The name of a domain.

       

      Type: String

      

      

    AutoRenew -> (boolean)

      

      Indicates whether the domain is automatically renewed upon expiration.

       

      Type: Boolean

       

      Valid values: ``True`` | ``False`` 

      

      

    TransferLock -> (boolean)

      

      Indicates whether a domain is locked from unauthorized transfer to another party.

       

      Type: Boolean

       

      Valid values: ``True`` | ``False`` 

      

      

    Expiry -> (timestamp)

      

      Expiration date of the domain in Coordinated Universal Time (UTC).

       

      Type: Long

      

      

    

  

NextPageMarker -> (string)

  

  If there are more domains than you specified for ``MaxItems`` in the request, submit another request and include the value of ``NextPageMarker`` in the value of ``Marker`` .

   

  Type: String

   

  Parent: ``Operations`` 

  

  

