[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms describe-connections:


********************
describe-connections
********************



===========
Description
===========



Describes the status of the connections that have been made between the replication instance and an endpoint. Connections are created when you test an endpoint.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DescribeConnections>`_


========
Synopsis
========

::

    describe-connections
  [--filters <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  The filters applied to the connection.

   

  Valid filter names: endpoint-arn | replication-instance-arn

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--marker`` (string)


  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command describes connections for an endpoint specified by ARN::

  aws dms describe-connections --filters Name="endpoint-arn",Values="arn:aws:dms:us-east-1:123456789012:endpoint:ZW5UAN6P4E77EC7YWHK4RZZ3BE"

Output::

  {
    "Connections": [
      {
        "Status": "successful",
        "ReplicationInstanceIdentifier": "test",
        "EndpointArn": "arn:aws:dms:us-east-arn:aws:dms:us-east-1:123456789012:endpoint:ZW5UAN6P4E77EC7YWHK4RZZ3BE",
        "EndpointIdentifier": "testsrc1",
        "ReplicationInstanceArn": "arn:aws:dms:us-east-1:123456789012:rep:6UTDJGBOUS3VI3SUWA66XFJCJQ"
      }
    ]
  }


======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

Connections -> (list)

  

  A description of the connections.

  

  (structure)

    

    

    

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

      

      

    

  

