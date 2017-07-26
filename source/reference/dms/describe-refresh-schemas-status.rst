[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms describe-refresh-schemas-status:


*******************************
describe-refresh-schemas-status
*******************************



===========
Description
===========



Returns the status of the refresh-schemas operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DescribeRefreshSchemasStatus>`_


========
Synopsis
========

::

    describe-refresh-schemas-status
  --endpoint-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--endpoint-arn`` (string)


  The Amazon Resource Name (ARN) string that uniquely identifies the endpoint.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

RefreshSchemasStatus -> (structure)

  

  The status of the schema.

  

  EndpointArn -> (string)

    

    The Amazon Resource Name (ARN) string that uniquely identifies the endpoint.

    

    

  ReplicationInstanceArn -> (string)

    

    The Amazon Resource Name (ARN) of the replication instance.

    

    

  Status -> (string)

    

    The status of the schema.

    

    

  LastRefreshDate -> (timestamp)

    

    The date the schema was last refreshed.

    

    

  LastFailureMessage -> (string)

    

    The last failure message for the schema.

    

    

  

