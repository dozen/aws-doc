[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es list-elasticsearch-versions:


***************************
list-elasticsearch-versions
***************************



===========
Description
===========



List all supported Elasticsearch versions



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/es-2015-01-01/ListElasticsearchVersions>`_


========
Synopsis
========

::

    list-elasticsearch-versions
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-results`` (integer)


  Set this value to limit the number of results returned. Value provided must be greater than 10 else it wont be honored. 

  

``--next-token`` (string)


  Paginated APIs accepts next-token input to returns next page results and provides a next-token output in the response which can be used by the client to retrieve more results. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ElasticsearchVersions -> (list)

  

  List of supported elastic search versions. 

  

  (string)

    

    

  

NextToken -> (string)

  

  Paginated APIs accepts next-token input to returns next page results and provides a next-token output in the response which can be used by the client to retrieve more results. 

  

  

