[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning describe-data-sources:


*********************
describe-data-sources
*********************



===========
Description
===========



Returns a list of ``DataSource`` that match the search criteria in the request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/DescribeDataSources>`_


``describe-data-sources`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Results``


========
Synopsis
========

::

    describe-data-sources
  [--filter-variable <value>]
  [--eq <value>]
  [--gt <value>]
  [--lt <value>]
  [--ge <value>]
  [--le <value>]
  [--ne <value>]
  [--prefix <value>]
  [--sort-order <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filter-variable`` (string)


  Use one of the following variables to filter a list of ``DataSource`` :

   

   
  * ``CreatedAt`` - Sets the search criteria to ``DataSource`` creation dates.
   
  * ``Status`` - Sets the search criteria to ``DataSource`` statuses.
   
  * ``Name`` - Sets the search criteria to the contents of ``DataSource``  ****  ``Name`` .
   
  * ``DataUri`` - Sets the search criteria to the URI of data files used to create the ``DataSource`` . The URI can identify either a file or an Amazon Simple Storage Service (Amazon S3) bucket or directory.
   
  * ``IAMUser`` - Sets the search criteria to the user account that invoked the ``DataSource`` creation.
   

  

  Possible values:

  
  *   ``CreatedAt``

  
  *   ``LastUpdatedAt``

  
  *   ``Status``

  
  *   ``Name``

  
  *   ``DataLocationS3``

  
  *   ``IAMUser``

  

  

``--eq`` (string)


  The equal to operator. The ``DataSource`` results will have ``FilterVariable`` values that exactly match the value specified with ``EQ`` .

  

``--gt`` (string)


  The greater than operator. The ``DataSource`` results will have ``FilterVariable`` values that are greater than the value specified with ``GT`` .

  

``--lt`` (string)


  The less than operator. The ``DataSource`` results will have ``FilterVariable`` values that are less than the value specified with ``LT`` .

  

``--ge`` (string)


  The greater than or equal to operator. The ``DataSource`` results will have ``FilterVariable`` values that are greater than or equal to the value specified with ``GE`` . 

  

``--le`` (string)


  The less than or equal to operator. The ``DataSource`` results will have ``FilterVariable`` values that are less than or equal to the value specified with ``LE`` .

  

``--ne`` (string)


  The not equal to operator. The ``DataSource`` results will have ``FilterVariable`` values not equal to the value specified with ``NE`` .

  

``--prefix`` (string)


  A string that is found at the beginning of a variable, such as ``Name`` or ``Id`` .

   

  For example, a ``DataSource`` could have the ``Name``  ``2014-09-09-HolidayGiftMailer`` . To search for this ``DataSource`` , select ``Name`` for the ``FilterVariable`` and any of the following strings for the ``Prefix`` : 

   

   
  * 2014-09
   
  * 2014-09-09
   
  * 2014-09-09-Holiday
   

  

``--sort-order`` (string)


  A two-value parameter that determines the sequence of the resulting list of ``DataSource`` .

   

   
  * ``asc`` - Arranges the list in ascending order (A-Z, 0-9).
   
  * ``dsc`` - Arranges the list in descending order (Z-A, 9-0).
   

   

  Results are sorted by ``FilterVariable`` .

  

  Possible values:

  
  *   ``asc``

  
  *   ``dsc``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Results -> (list)

  

  A list of ``DataSource`` that meet the search criteria. 

  

  (structure)

    

    Represents the output of the ``get-data-source`` operation. 

     

    The content consists of the detailed metadata and data file information and the current status of the ``DataSource`` . 

    

    DataSourceId -> (string)

      

      The ID that is assigned to the ``DataSource`` during creation.

      

      

    DataLocationS3 -> (string)

      

      The location and name of the data in Amazon Simple Storage Service (Amazon S3) that is used by a ``DataSource`` .

      

      

    DataRearrangement -> (string)

      

      A JSON string that represents the splitting and rearrangement requirement used when this ``DataSource`` was created.

      

      

    CreatedByIamUser -> (string)

      

      The AWS user account from which the ``DataSource`` was created. The account type can be either an AWS root account or an AWS Identity and Access Management (IAM) user account.

      

      

    CreatedAt -> (timestamp)

      

      The time that the ``DataSource`` was created. The time is expressed in epoch time.

      

      

    LastUpdatedAt -> (timestamp)

      

      The time of the most recent edit to the ``BatchPrediction`` . The time is expressed in epoch time.

      

      

    DataSizeInBytes -> (long)

      

      The total number of observations contained in the data files that the ``DataSource`` references.

      

      

    NumberOfFiles -> (long)

      

      The number of data files referenced by the ``DataSource`` .

      

      

    Name -> (string)

      

      A user-supplied name or description of the ``DataSource`` .

      

      

    Status -> (string)

      

      The current status of the ``DataSource`` . This element can have one of the following values: 

       

       
      * PENDING - Amazon Machine Learning (Amazon ML) submitted a request to create a ``DataSource`` .
       
      * INPROGRESS - The creation process is underway.
       
      * FAILED - The request to create a ``DataSource`` did not run to completion. It is not usable.
       
      * COMPLETED - The creation process completed successfully.
       
      * DELETED - The ``DataSource`` is marked as deleted. It is not usable.
       

      

      

    Message -> (string)

      

      A description of the most recent details about creating the ``DataSource`` .

      

      

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

        

        The SQL query that is specified during  create-data-source-from-redshift . Returns only if ``Verbose`` is true in GetDataSourceInput. 

        

        

      

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

        

        The SQL query that is supplied during  create-data-source-from-rds . Returns only if ``Verbose`` is true in ``GetDataSourceInput`` . 

        

        

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

      

      Long integer type that is a 64-bit signed number.

      

      

    FinishedAt -> (timestamp)

      

      A timestamp represented in epoch time.

      

      

    StartedAt -> (timestamp)

      

      A timestamp represented in epoch time.

      

      

    

  

NextToken -> (string)

  

  An ID of the next page in the paginated results that indicates at least one more page follows.

  

  

