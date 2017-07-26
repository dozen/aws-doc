[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning create-data-source-from-rds:


***************************
create-data-source-from-rds
***************************



===========
Description
===========



Creates a ``DataSource`` object from an `Amazon Relational Database Service <http://aws.amazon.com/rds/>`_ (Amazon RDS). A ``DataSource`` references data that can be used to perform ``create-ml-model`` , ``create-evaluation`` , or ``create-batch-prediction`` operations.

 

``create-data-source-from-rds`` is an asynchronous operation. In response to ``create-data-source-from-rds`` , Amazon Machine Learning (Amazon ML) immediately returns and sets the ``DataSource`` status to ``PENDING`` . After the ``DataSource`` is created and ready for use, Amazon ML sets the ``Status`` parameter to ``COMPLETED`` . ``DataSource`` in the ``COMPLETED`` or ``PENDING`` state can be used only to perform ``create-ml-model`` , ``create-evaluation`` , or ``create-batch-prediction`` operations. 

 

If Amazon ML cannot accept the input source, it sets the ``Status`` parameter to ``FAILED`` and includes an error message in the ``Message`` attribute of the ``get-data-source`` operation response. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/CreateDataSourceFromRDS>`_


========
Synopsis
========

::

    create-data-source-from-rds
  --data-source-id <value>
  [--data-source-name <value>]
  --rds-data <value>
  --role-arn <value>
  [--compute-statistics | --no-compute-statistics]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--data-source-id`` (string)


  A user-supplied ID that uniquely identifies the ``DataSource`` . Typically, an Amazon Resource Number (ARN) becomes the ID for a ``DataSource`` .

  

``--data-source-name`` (string)


  A user-supplied name or description of the ``DataSource`` .

  

``--rds-data`` (structure)


  The data specification of an Amazon RDS ``DataSource`` :

   

   
  * DatabaseInformation - 

     
    * ``DatabaseName`` - The name of the Amazon RDS database.
     
    * ``InstanceIdentifier`` - A unique identifier for the Amazon RDS database instance.
     

   

  
   
  * DatabaseCredentials - AWS Identity and Access Management (IAM) credentials that are used to connect to the Amazon RDS database.
   
  * ResourceRole - A role (DataPipelineDefaultResourceRole) assumed by an EC2 instance to carry out the copy task from Amazon RDS to Amazon Simple Storage Service (Amazon S3). For more information, see `Role templates <http://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-iam-roles.html>`_ for data pipelines.
   
  * ServiceRole - A role (DataPipelineDefaultRole) assumed by the AWS Data Pipeline service to monitor the progress of the copy task from Amazon RDS to Amazon S3. For more information, see `Role templates <http://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-iam-roles.html>`_ for data pipelines.
   
  * SecurityInfo - The security information to use to access an RDS DB instance. You need to set up appropriate ingress rules for the security entity IDs provided to allow access to the Amazon RDS instance. Specify a [``SubnetId`` , ``SecurityGroupIds`` ] pair for a VPC-based RDS DB instance.
   
  * SelectSqlQuery - A query that is used to retrieve the observation data for the ``Datasource`` .
   
  * S3StagingLocation - The Amazon S3 location for staging Amazon RDS data. The data retrieved from Amazon RDS using ``SelectSqlQuery`` is stored in this location.
   
  * DataSchemaUri - The Amazon S3 location of the ``DataSchema`` .
   
  * DataSchema - A JSON string representing the schema. This is not required if ``DataSchemaUri`` is specified. 
   
  * DataRearrangement - A JSON string that represents the splitting and rearrangement requirements for the ``Datasource`` .   Sample - ``"{\"splitting\":{\"percentBegin\":10,\"percentEnd\":60}}"``   
   

  



Shorthand Syntax::

    DatabaseInformation={InstanceIdentifier=string,DatabaseName=string},SelectSqlQuery=string,DatabaseCredentials={Username=string,Password=string},S3StagingLocation=string,DataRearrangement=string,DataSchema=string,DataSchemaUri=string,ResourceRole=string,ServiceRole=string,SubnetId=string,SecurityGroupIds=string,string




JSON Syntax::

  {
    "DatabaseInformation": {
      "InstanceIdentifier": "string",
      "DatabaseName": "string"
    },
    "SelectSqlQuery": "string",
    "DatabaseCredentials": {
      "Username": "string",
      "Password": "string"
    },
    "S3StagingLocation": "string",
    "DataRearrangement": "string",
    "DataSchema": "string",
    "DataSchemaUri": "string",
    "ResourceRole": "string",
    "ServiceRole": "string",
    "SubnetId": "string",
    "SecurityGroupIds": ["string", ...]
  }



``--role-arn`` (string)


  The role that Amazon ML assumes on behalf of the user to create and activate a data pipeline in the user's account and copy data using the ``SelectSqlQuery`` query from Amazon RDS to Amazon S3.

   

   

  

``--compute-statistics`` | ``--no-compute-statistics`` (boolean)


  The compute statistics for a ``DataSource`` . The statistics are generated from the observation data referenced by a ``DataSource`` . Amazon ML uses the statistics internally during ``MLModel`` training. This parameter must be set to ``true`` if the ```` DataSource```` needs to be used for ``MLModel`` training. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DataSourceId -> (string)

  

  A user-supplied ID that uniquely identifies the datasource. This value should be identical to the value of the ``DataSourceID`` in the request. 

  

  

