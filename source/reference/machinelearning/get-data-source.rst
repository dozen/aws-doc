[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning get-data-source:


***************
get-data-source
***************



===========
Description
===========



Returns a ``DataSource`` that includes metadata and data file information, as well as the current status of the ``DataSource`` .

 

``get-data-source`` provides results in normal or verbose format. The verbose format adds the schema description and the list of files pointed to by the DataSource to the normal format.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/GetDataSource>`_


========
Synopsis
========

::

    get-data-source
  --data-source-id <value>
  [--verbose | --no-verbose]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--data-source-id`` (string)


  The ID assigned to the ``DataSource`` at creation.

  

``--verbose`` | ``--no-verbose`` (boolean)


  Specifies whether the ``get-data-source`` operation should return ``DataSourceSchema`` .

   

  If true, ``DataSourceSchema`` is returned.

   

  If false, ``DataSourceSchema`` is not returned.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DataSourceId -> (string)

  

  The ID assigned to the ``DataSource`` at creation. This value should be identical to the value of the ``DataSourceId`` in the request.

  

  

DataLocationS3 -> (string)

  

  The location of the data file or directory in Amazon Simple Storage Service (Amazon S3).

  

  

DataRearrangement -> (string)

  

  A JSON string that represents the splitting and rearrangement requirement used when this ``DataSource`` was created.

  

  

CreatedByIamUser -> (string)

  

  The AWS user account from which the ``DataSource`` was created. The account type can be either an AWS root account or an AWS Identity and Access Management (IAM) user account.

  

  

CreatedAt -> (timestamp)

  

  The time that the ``DataSource`` was created. The time is expressed in epoch time.

  

  

LastUpdatedAt -> (timestamp)

  

  The time of the most recent edit to the ``DataSource`` . The time is expressed in epoch time.

  

  

DataSizeInBytes -> (long)

  

  The total size of observations in the data files.

  

  

NumberOfFiles -> (long)

  

  The number of data files referenced by the ``DataSource`` .

  

  

Name -> (string)

  

  A user-supplied name or description of the ``DataSource`` .

  

  

Status -> (string)

  

  The current status of the ``DataSource`` . This element can have one of the following values:

   

   
  * ``PENDING`` - Amazon ML submitted a request to create a ``DataSource`` .
   
  * ``INPROGRESS`` - The creation process is underway.
   
  * ``FAILED`` - The request to create a ``DataSource`` did not run to completion. It is not usable.
   
  * ``COMPLETED`` - The creation process completed successfully.
   
  * ``DELETED`` - The ``DataSource`` is marked as deleted. It is not usable.
   

  

  

LogUri -> (string)

  

  A link to the file containing logs of ``CreateDataSourceFrom*`` operations.

  

  

Message -> (string)

  

  The user-supplied description of the most recent details about creating the ``DataSource`` .

  

  

RedshiftMetadata -> (structure)

  

  Describes the ``DataSource`` details specific to Amazon Redshift.

  

  RedshiftDatabase -> (structure)

    

    Describes the database details required to connect to an Amazon Redshift database.

    

    DatabaseName -> (string)

      

      The name of a database hosted on an Amazon Redshift cluster.

      

      

    ClusterIdentifier -> (string)

      

      The ID of an Amazon Redshift cluster.

      

      

    

  DatabaseUserName -> (string)

    

    A username to be used by Amazon Machine Learning (Amazon ML)to connect to a database on an Amazon Redshift cluster. The username should have sufficient permissions to execute the ``RedshiftSelectSqlQuery`` query. The username should be valid for an Amazon Redshift `USER <http://docs.aws.amazon.com/redshift/latest/dg/r_CREATE_USER.html>`_ .

    

    

  SelectSqlQuery -> (string)

    

    The SQL query that is specified during  create-data-source-from-redshift . Returns only if ``verbose`` is true in GetDataSourceInput. 

    

    

  

RDSMetadata -> (structure)

  

  The datasource details that are specific to Amazon RDS.

  

  Database -> (structure)

    

    The database details required to connect to an Amazon RDS.

    

    InstanceIdentifier -> (string)

      

      The ID of an RDS DB instance.

      

      

    DatabaseName -> (string)

      

      The name of a database hosted on an RDS DB instance.

      

      

    

  DatabaseUserName -> (string)

    

    The username to be used by Amazon ML to connect to database on an Amazon RDS instance. The username should have sufficient permissions to execute an ``RDSSelectSqlQuery`` query.

    

    

  SelectSqlQuery -> (string)

    

    The SQL query that is supplied during  create-data-source-from-rds . Returns only if ``verbose`` is true in ``GetDataSourceInput`` . 

    

    

  ResourceRole -> (string)

    

    The role (DataPipelineDefaultResourceRole) assumed by an Amazon EC2 instance to carry out the copy task from Amazon RDS to Amazon S3. For more information, see `Role templates <http://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-iam-roles.html>`_ for data pipelines.

    

    

  ServiceRole -> (string)

    

    The role (DataPipelineDefaultRole) assumed by the Data Pipeline service to monitor the progress of the copy task from Amazon RDS to Amazon S3. For more information, see `Role templates <http://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-iam-roles.html>`_ for data pipelines.

    

    

  DataPipelineId -> (string)

    

    The ID of the Data Pipeline instance that is used to carry to copy data from Amazon RDS to Amazon S3. You can use the ID to find details about the instance in the Data Pipeline console.

    

    

  

RoleARN -> (string)

  

  The Amazon Resource Name (ARN) of an `AWS IAM Role <http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-toplevel.html#roles-about-termsandconcepts>`_ , such as the following: arn:aws:iam::account:role/rolename. 

  

  

ComputeStatistics -> (boolean)

  

  The parameter is ``true`` if statistics need to be generated from the observation data. 

  

  

ComputeTime -> (long)

  

  The approximate CPU time in milliseconds that Amazon Machine Learning spent processing the ``DataSource`` , normalized and scaled on computation resources. ``ComputeTime`` is only available if the ``DataSource`` is in the ``COMPLETED`` state and the ``ComputeStatistics`` is set to true.

  

  

FinishedAt -> (timestamp)

  

  The epoch time when Amazon Machine Learning marked the ``DataSource`` as ``COMPLETED`` or ``FAILED`` . ``FinishedAt`` is only available when the ``DataSource`` is in the ``COMPLETED`` or ``FAILED`` state.

  

  

StartedAt -> (timestamp)

  

  The epoch time when Amazon Machine Learning marked the ``DataSource`` as ``INPROGRESS`` . ``StartedAt`` isn't available if the ``DataSource`` is in the ``PENDING`` state.

  

  

DataSourceSchema -> (string)

  

  The schema used by all of the data files of this ``DataSource`` .

   

  .. note::

    Note 

    This parameter is provided as part of the verbose format.

    

  

  

