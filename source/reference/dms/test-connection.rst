[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms test-connection:


***************
test-connection
***************



===========
Description
===========



Tests the connection between the replication instance and the endpoint.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/TestConnection>`_


========
Synopsis
========

::

    test-connection
  --replication-instance-arn <value>
  --endpoint-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-instance-arn`` (string)


  The Amazon Resource Name (ARN) of the replication instance.

  

``--endpoint-arn`` (string)


  The Amazon Resource Name (ARN) string that uniquely identifies the endpoint.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Connection -> (structure)

  

  The connection tested.

  

  ReplicationInstanceArn -> (string)

    

    The Amazon Resource Name (ARN) of the replication instance.

    

    

  EndpointArn -> (string)

    

    The Amazon Resource Name (ARN) string that uniquely identifies the endpoint.

    

    

  Status -> (string)

    

    The connection status.

    

    

  LastFailureMessage -> (string)

    

    The error message when the connection last failed.

    

    

  EndpointIdentifier -> (string)

    

    The identifier of the endpoint. Identifiers must begin with a letter; must contain only ASCII letters, digits, and hyphens; and must not end with a hyphen or contain two consecutive hyphens.

    

    

  ReplicationInstanceIdentifier -> (string)

    

    The replication instance identifier. This parameter is stored as a lowercase string.

    

    

  

