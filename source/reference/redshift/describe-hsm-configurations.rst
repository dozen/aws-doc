[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-hsm-configurations:


***************************
describe-hsm-configurations
***************************



===========
Description
===========



Returns information about the specified Amazon Redshift HSM configuration. If no configuration ID is specified, returns information about all the HSM configurations owned by your AWS customer account.

 

If you specify both tag keys and tag values in the same request, Amazon Redshift returns all HSM connections that match any combination of the specified keys and values. For example, if you have ``owner`` and ``environment`` for tag keys, and ``admin`` and ``test`` for tag values, all HSM connections that have any combination of those values are returned.

 

If both tag keys and values are omitted from the request, HSM connections are returned regardless of whether they have tag keys or values associated with them.



``describe-hsm-configurations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``HsmConfigurations``


========
Synopsis
========

::

    describe-hsm-configurations
  [--hsm-configuration-identifier <value>]
  [--tag-keys <value>]
  [--tag-values <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--hsm-configuration-identifier`` (string)


  The identifier of a specific Amazon Redshift HSM configuration to be described. If no identifier is specified, information is returned for all HSM configurations owned by your AWS customer account.

  

``--tag-keys`` (list)


  A tag key or keys for which you want to return all matching HSM configurations that are associated with the specified key or keys. For example, suppose that you have HSM configurations that are tagged with keys called ``owner`` and ``environment`` . If you specify both of these tag keys in the request, Amazon Redshift returns a response with the HSM configurations that have either or both of these tag keys associated with them.

  



Syntax::

  "string" "string" ...



``--tag-values`` (list)


  A tag value or values for which you want to return all matching HSM configurations that are associated with the specified tag value or values. For example, suppose that you have HSM configurations that are tagged with values called ``admin`` and ``test`` . If you specify both of these tag values in the request, Amazon Redshift returns a response with the HSM configurations that have either or both of these tag values associated with them.

  



Syntax::

  "string" "string" ...



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

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  

HsmConfigurations -> (list)

  

  A list of Amazon Redshift HSM configurations.

  

  (structure)

    

    Returns information about an HSM configuration, which is an object that describes to Amazon Redshift clusters the information they require to connect to an HSM where they can store database encryption keys.

    

    HsmConfigurationIdentifier -> (string)

      

      The name of the Amazon Redshift HSM configuration.

      

      

    Description -> (string)

      

      A text description of the HSM configuration.

      

      

    HsmIpAddress -> (string)

      

      The IP address that the Amazon Redshift cluster must use to access the HSM.

      

      

    HsmPartitionName -> (string)

      

      The name of the partition in the HSM where the Amazon Redshift clusters will store their database encryption keys.

      

      

    Tags -> (list)

      

      The list of tags for the HSM configuration.

      

      (structure)

        

        A tag consisting of a name/value pair for a resource.

        

        Key -> (string)

          

          The key, or name, for the resource tag.

          

          

        Value -> (string)

          

          The value for the resource tag.

          

          

        

      

    

  

