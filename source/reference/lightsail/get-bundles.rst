[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-bundles:


***********
get-bundles
***********



===========
Description
===========



Returns the list of bundles that are available for purchase. A bundle describes the specs for your virtual private server (or *instance* ).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetBundles>`_


``get-bundles`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``bundles``


========
Synopsis
========

::

    get-bundles
  [--include-inactive | --no-include-inactive]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--include-inactive`` | ``--no-include-inactive`` (boolean)


  A Boolean value that indicates whether to include inactive bundle results in your request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON page-token provided. The JSON page-token follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

bundles -> (list)

  

  An array of key-value pairs that contains information about the available bundles.

  

  (structure)

    

    Describes a bundle, which is a set of specs describing your virtual private server (or *instance* ).

    

    price -> (float)

      

      The price in US dollars (e.g., ``5.0`` ).

      

      

    cpuCount -> (integer)

      

      The number of vCPUs included in the bundle (e.g., ``2`` ).

      

      

    diskSizeInGb -> (integer)

      

      The size of the SSD (e.g., ``30`` ).

      

      

    bundleId -> (string)

      

      The bundle ID (e.g., ``micro_1_0`` ).

      

      

    instanceType -> (string)

      

      The Amazon EC2 instance type (e.g., ``t2.micro`` ).

      

      

    isActive -> (boolean)

      

      A Boolean value indicating whether the bundle is active.

      

      

    name -> (string)

      

      A friendly name for the bundle (e.g., ``Micro`` ).

      

      

    power -> (integer)

      

      The power of the bundle (e.g., ``500`` ).

      

      

    ramSizeInGb -> (float)

      

      The amount of RAM in GB (e.g., ``2.0`` ).

      

      

    transferPerMonthInGb -> (integer)

      

      The data transfer rate per month in GB (e.g., ``2000`` ).

      

      

    

  

nextPageToken -> (string)

  

  A token used for advancing to the next page of results from your get active names request.

  

  

