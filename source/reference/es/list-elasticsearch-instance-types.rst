[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es list-elasticsearch-instance-types:


*********************************
list-elasticsearch-instance-types
*********************************



===========
Description
===========



List all Elasticsearch instance types that are supported for given ElasticsearchVersion



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/es-2015-01-01/ListElasticsearchInstanceTypes>`_


========
Synopsis
========

::

    list-elasticsearch-instance-types
  --elasticsearch-version <value>
  [--domain-name <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--elasticsearch-version`` (string)


  Version of Elasticsearch for which list of supported elasticsearch instance types are needed. 

  

``--domain-name`` (string)


  domain-name represents the name of the Domain that we are trying to modify. This should be present only if we are querying for list of available Elasticsearch instance types when modifying existing domain. 

  

``--max-results`` (integer)


  Set this value to limit the number of results returned. Value provided must be greater than 30 else it wont be honored. 

  

``--next-token`` (string)


  next-token should be sent in case if earlier API call produced result containing NextToken. It is used for pagination. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ElasticsearchInstanceTypes -> (list)

  

  List of instance types supported by Amazon Elasticsearch service for given ``  ElasticsearchVersion ``  

  

  (string)

    

    

  

NextToken -> (string)

  

  In case if there are more results available next-token would be present, make further request to the same API with received next-token to paginate remaining results. 

  

  

