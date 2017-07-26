[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms modify-endpoint:


***************
modify-endpoint
***************



===========
Description
===========



Modifies the specified endpoint.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/ModifyEndpoint>`_


========
Synopsis
========

::

    modify-endpoint
  --endpoint-arn <value>
  [--endpoint-identifier <value>]
  [--endpoint-type <value>]
  [--engine-name <value>]
  [--username <value>]
  [--password <value>]
  [--server-name <value>]
  [--port <value>]
  [--database-name <value>]
  [--extra-connection-attributes <value>]
  [--certificate-arn <value>]
  [--ssl-mode <value>]
  [--dynamo-db-settings <value>]
  [--s3-settings <value>]
  [--mongo-db-settings <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--endpoint-arn`` (string)


  The Amazon Resource Name (ARN) string that uniquely identifies the endpoint.

  

``--endpoint-identifier`` (string)


  The database endpoint identifier. Identifiers must begin with a letter; must contain only ASCII letters, digits, and hyphens; and must not end with a hyphen or contain two consecutive hyphens.

  

``--endpoint-type`` (string)


  The type of endpoint.

  

  Possible values:

  
  *   ``source``

  
  *   ``target``

  

  

``--engine-name`` (string)


  The type of engine for the endpoint. Valid values, depending on the EndPointType, include MYSQL, ORACLE, POSTGRES, MARIADB, AURORA, REDSHIFT, S3, DYNAMODB, MONGODB, SYBASE, and SQLSERVER.

  

``--username`` (string)


  The user name to be used to login to the endpoint database.

  

``--password`` (string)


  The password to be used to login to the endpoint database.

  

``--server-name`` (string)


  The name of the server where the endpoint database resides.

  

``--port`` (integer)


  The port used by the endpoint database.

  

``--database-name`` (string)


  The name of the endpoint database.

  

``--extra-connection-attributes`` (string)


  Additional attributes associated with the connection.

  

``--certificate-arn`` (string)


  The Amazon Resource Name (ARN) of the certificate used for SSL connection.

  

``--ssl-mode`` (string)


  The SSL mode to be used.

   

  SSL mode can be one of four values: none, require, verify-ca, verify-full. 

   

  The default value is none.

  

  Possible values:

  
  *   ``none``

  
  *   ``require``

  
  *   ``verify-ca``

  
  *   ``verify-full``

  

  

``--dynamo-db-settings`` (structure)


  Settings in JSON format for the target Amazon DynamoDB endpoint. For more information about the available settings, see the **Using Object Mapping to Migrate Data to DynamoDB** section at `Using an Amazon DynamoDB Database as a Target for AWS Database Migration Service <http://docs.aws.amazon.com/dms/latest/userguide/CHAP_Target.DynamoDB.html>`_ . 

  



Shorthand Syntax::

    ServiceAccessRoleArn=string




JSON Syntax::

  {
    "ServiceAccessRoleArn": "string"
  }



``--s3-settings`` (structure)


  Settings in JSON format for the target S3 endpoint. For more information about the available settings, see the **Extra Connection Attributes** section at `Using Amazon S3 as a Target for AWS Database Migration Service <http://docs.aws.amazon.com/dms/latest/userguide/CHAP_Target.S3.html>`_ . 

  



Shorthand Syntax::

    ServiceAccessRoleArn=string,ExternalTableDefinition=string,CsvRowDelimiter=string,CsvDelimiter=string,BucketFolder=string,BucketName=string,CompressionType=string




JSON Syntax::

  {
    "ServiceAccessRoleArn": "string",
    "ExternalTableDefinition": "string",
    "CsvRowDelimiter": "string",
    "CsvDelimiter": "string",
    "BucketFolder": "string",
    "BucketName": "string",
    "CompressionType": "none"|"gzip"
  }



``--mongo-db-settings`` (structure)


  Settings in JSON format for the source MongoDB endpoint. For more information about the available settings, see the **Configuration Properties When Using MongoDB as a Source for AWS Database Migration Service** section at `Using Amazon S3 as a Target for AWS Database Migration Service <http://docs.aws.amazon.com/dms/latest/userguide/CHAP_Source.MongoDB.html>`_ . 

  



Shorthand Syntax::

    Username=string,Password=string,ServerName=string,Port=integer,DatabaseName=string,AuthType=string,AuthMechanism=string,NestingLevel=string,ExtractDocId=string,DocsToInvestigate=string,AuthSource=string




JSON Syntax::

  {
    "Username": "string",
    "Password": "string",
    "ServerName": "string",
    "Port": integer,
    "DatabaseName": "string",
    "AuthType": "no"|"password",
    "AuthMechanism": "default"|"mongodb_cr"|"scram_sha_1",
    "NestingLevel": "none"|"one",
    "ExtractDocId": "string",
    "DocsToInvestigate": "string",
    "AuthSource": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Endpoint -> (structure)

  

  The modified endpoint.

  

  EndpointIdentifier -> (string)

    

    The database endpoint identifier. Identifiers must begin with a letter; must contain only ASCII letters, digits, and hyphens; and must not end with a hyphen or contain two consecutive hyphens.

    

    

  EndpointType -> (string)

    

    The type of endpoint.

    

    

  EngineName -> (string)

    

    The database engine name. Valid values, depending on the EndPointType, include MYSQL, ORACLE, POSTGRES, MARIADB, AURORA, REDSHIFT, S3, SYBASE, DYNAMODB, MONGODB, and SQLSERVER.

    

    

  Username -> (string)

    

    The user name used to connect to the endpoint.

    

    

  ServerName -> (string)

    

    The name of the server at the endpoint.

    

    

  Port -> (integer)

    

    The port value used to access the endpoint.

    

    

  DatabaseName -> (string)

    

    The name of the database at the endpoint.

    

    

  ExtraConnectionAttributes -> (string)

    

    Additional connection attributes used to connect to the endpoint.

    

    

  Status -> (string)

    

    The status of the endpoint.

    

    

  KmsKeyId -> (string)

    

    The KMS key identifier that will be used to encrypt the connection parameters. If you do not specify a value for the KmsKeyId parameter, then AWS DMS will use your default encryption key. AWS KMS creates the default encryption key for your AWS account. Your AWS account has a different default encryption key for each AWS region.

    

    

  EndpointArn -> (string)

    

    The Amazon Resource Name (ARN) string that uniquely identifies the endpoint.

    

    

  CertificateArn -> (string)

    

    The Amazon Resource Name (ARN) used for SSL connection to the endpoint.

    

    

  SslMode -> (string)

    

    The SSL mode used to connect to the endpoint.

     

    SSL mode can be one of four values: none, require, verify-ca, verify-full. 

     

    The default value is none.

    

    

  ExternalId -> (string)

    

    Value returned by a call to create-endpoint that can be used for cross-account validation. Use it on a subsequent call to create-endpoint to create the endpoint with a cross-account. 

    

    

  DynamoDbSettings -> (structure)

    

    The settings for the target DynamoDB database. For more information, see the ``DynamoDBSettings`` structure.

    

    ServiceAccessRoleArn -> (string)

      

      The Amazon Resource Name (ARN) used by the service access IAM role. 

      

      

    

  S3Settings -> (structure)

    

    The settings for the S3 target endpoint. For more information, see the ``s3-settings`` structure.

    

    ServiceAccessRoleArn -> (string)

      

      The Amazon Resource Name (ARN) used by the service access IAM role. 

      

      

    ExternalTableDefinition -> (string)

      

       

      

      

    CsvRowDelimiter -> (string)

      

      The delimiter used to separate rows in the source files. The default is a carriage return (\n). 

      

      

    CsvDelimiter -> (string)

      

      The delimiter used to separate columns in the source files. The default is a comma. 

      

      

    BucketFolder -> (string)

      

      An optional parameter to set a folder name in the S3 bucket. If provided, tables are created in the path bucketFolder/schema_name/table_name/. If this parameter is not specified, then the path used is schema_name/table_name/. 

      

      

    BucketName -> (string)

      

      The name of the S3 bucket. 

      

      

    CompressionType -> (string)

      

      An optional parameter to use GZIP to compress the target files. Set to GZIP to compress the target files. Set to NONE (the default) or do not use to leave the files uncompressed. 

      

      

    

  MongoDbSettings -> (structure)

    

    The settings for the MongoDB source endpoint. For more information, see the ``mongo-db-settings`` structure.

    

    Username -> (string)

      

      The user name you use to access the MongoDB source endpoint. 

      

      

    Password -> (string)

      

      The password for the user account you use to access the MongoDB source endpoint. 

      

      

    ServerName -> (string)

      

      The name of the server on the MongoDB source endpoint. 

      

      

    Port -> (integer)

      

      The port value for the MongoDB source endpoint. 

      

      

    DatabaseName -> (string)

      

      The database name on the MongoDB source endpoint. 

      

      

    AuthType -> (string)

      

      The authentication type you use to access the MongoDB source endpoint.

       

      Valid values: NO, PASSWORD 

       

      When NO is selected, user name and password parameters are not used and can be empty. 

      

      

    AuthMechanism -> (string)

      

      The authentication mechanism you use to access the MongoDB source endpoint.

       

      Valid values: DEFAULT, MONGODB_CR, SCRAM_SHA_1 

       

      DEFAULT – For MongoDB version 2.x, use MONGODB_CR. For MongoDB version 3.x, use SCRAM_SHA_1. This attribute is not used when authType=No.

      

      

    NestingLevel -> (string)

      

      Specifies either document or table mode. 

       

      Valid values: NONE, ONE

       

      Default value is NONE. Specify NONE to use document mode. Specify ONE to use table mode.

      

      

    ExtractDocId -> (string)

      

      Specifies the document ID. Use this attribute when ``NestingLevel`` is set to NONE. 

       

      Default value is false. 

      

      

    DocsToInvestigate -> (string)

      

      Indicates the number of documents to preview to determine the document organization. Use this attribute when ``NestingLevel`` is set to ONE. 

       

      Must be a positive value greater than 0. Default value is 1000.

      

      

    AuthSource -> (string)

      

      The MongoDB database name. This attribute is not used when ``authType=NO`` . 

       

      The default is admin.

      

      

    

  

