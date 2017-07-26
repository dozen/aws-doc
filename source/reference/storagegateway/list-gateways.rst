[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway list-gateways:


*************
list-gateways
*************



===========
Description
===========



This operation lists gateways owned by an AWS account in a region specified in the request. The returned list is ordered by gateway Amazon Resource Name (ARN).

 

By default, the operation returns a maximum of 100 gateways. This operation supports pagination that allows you to optionally reduce the number of gateways returned in a response.

 

If you have more gateways than are returned in a response-that is, the response returns only a truncated list of your gateways-the response contains a marker that you can specify in your next request to fetch the next page of gateways.



``list-gateways`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Gateways``


========
Synopsis
========

::

    list-gateways
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



========
Examples
========

**To list gateways for an account**

The following ``list-gateways`` command lists all the gateways defined for an account::

    aws storagegateway list-gateways

This command outputs a JSON block that contains a list of gateway Amazon Resource Names (ARNs).


======
Output
======

Gateways -> (list)

  

  (structure)

    

    GatewayARN -> (string)

      

      The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

      

      

    GatewayType -> (string)

      

      

    GatewayOperationalState -> (string)

      

      

    GatewayName -> (string)

      

      

    

  

Marker -> (string)

  

  

