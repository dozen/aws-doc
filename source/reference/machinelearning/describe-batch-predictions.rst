[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning describe-batch-predictions:


**************************
describe-batch-predictions
**************************



===========
Description
===========



Returns a list of ``BatchPrediction`` operations that match the search criteria in the request.



``describe-batch-predictions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Results``


========
Synopsis
========

::

    describe-batch-predictions
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
  [--generate-cli-skeleton]




=======
Options
=======

``--filter-variable`` (string)


  Use one of the following variables to filter a list of ``BatchPrediction`` :

   

   
  * ``CreatedAt`` - Sets the search criteria to the ``BatchPrediction`` creation date.
   
  * ``Status`` - Sets the search criteria to the ``BatchPrediction`` status.
   
  * ``Name`` - Sets the search criteria to the contents of the ``BatchPrediction`` ****  ``Name`` .
   
  * ``IAMUser`` - Sets the search criteria to the user account that invoked the ``BatchPrediction`` creation.
   
  * ``MLModelId`` - Sets the search criteria to the ``MLModel`` used in the ``BatchPrediction`` .
   
  * ``DataSourceId`` - Sets the search criteria to the ``DataSource`` used in the ``BatchPrediction`` .
   
  * ``DataURI`` - Sets the search criteria to the data file(s) used in the ``BatchPrediction`` . The URL can identify either a file or an Amazon Simple Storage Solution (Amazon S3) bucket or directory.
   

  

  Possible values:

  
  *   ``CreatedAt``

  
  *   ``LastUpdatedAt``

  
  *   ``Status``

  
  *   ``Name``

  
  *   ``IAMUser``

  
  *   ``MLModelId``

  
  *   ``DataSourceId``

  
  *   ``DataURI``

  

  

``--eq`` (string)


  The equal to operator. The ``BatchPrediction`` results will have ``FilterVariable`` values that exactly match the value specified with ``EQ`` .

  

``--gt`` (string)


  The greater than operator. The ``BatchPrediction`` results will have ``FilterVariable`` values that are greater than the value specified with ``GT`` .

  

``--lt`` (string)


  The less than operator. The ``BatchPrediction`` results will have ``FilterVariable`` values that are less than the value specified with ``LT`` .

  

``--ge`` (string)


  The greater than or equal to operator. The ``BatchPrediction`` results will have ``FilterVariable`` values that are greater than or equal to the value specified with ``GE`` . 

  

``--le`` (string)


  The less than or equal to operator. The ``BatchPrediction`` results will have ``FilterVariable`` values that are less than or equal to the value specified with ``LE`` .

  

``--ne`` (string)


  The not equal to operator. The ``BatchPrediction`` results will have ``FilterVariable`` values not equal to the value specified with ``NE`` .

  

``--prefix`` (string)


  A string that is found at the beginning of a variable, such as ``Name`` or ``Id`` .

   

  For example, a ``Batch Prediction`` operation could have the ``Name``  ``2014-09-09-HolidayGiftMailer`` . To search for this ``BatchPrediction`` , select ``Name`` for the ``FilterVariable`` and any of the following strings for the ``Prefix`` : 

   

   
  * 2014-09
   
  * 2014-09-09
   
  * 2014-09-09-Holiday
   

  

``--sort-order`` (string)


  A two-value parameter that determines the sequence of the resulting list of ``MLModel`` s.

   

   
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

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Results -> (list)

  

  A list of  BatchPrediction objects that meet the search criteria. 

  

  (structure)

    

    Represents the output of  get-batch-prediction operation.

     

    The content consists of the detailed metadata, the status, and the data file information of a *Batch Prediction* .

    

    BatchPredictionId -> (string)

      

      The ID assigned to the ``BatchPrediction`` at creation. This value should be identical to the value of the ``BatchPredictionID`` in the request. 

      

      

    MLModelId -> (string)

      

      The ID of the ``MLModel`` that generated predictions for the ``BatchPrediction`` request.

      

      

    BatchPredictionDataSourceId -> (string)

      

      The ID of the ``DataSource`` that points to the group of observations to predict.

      

      

    InputDataLocationS3 -> (string)

      

      The location of the data file or directory in Amazon Simple Storage Service (Amazon S3).

      

      

    CreatedByIamUser -> (string)

      

      The AWS user account that invoked the ``BatchPrediction`` . The account type can be either an AWS root account or an AWS Identity and Access Management (IAM) user account.

      

      

    CreatedAt -> (timestamp)

      

      The time that the ``BatchPrediction`` was created. The time is expressed in epoch time.

      

      

    LastUpdatedAt -> (timestamp)

      

      The time of the most recent edit to the ``BatchPrediction`` . The time is expressed in epoch time.

      

      

    Name -> (string)

      

      A user-supplied name or description of the ``BatchPrediction`` .

      

      

    Status -> (string)

      

      The status of the ``BatchPrediction`` . This element can have one of the following values:

       

       
      * ``PENDING`` - Amazon Machine Learning (Amazon ML) submitted a request to generate predictions for a batch of observations.
       
      * ``INPROGRESS`` - The process is underway.
       
      * ``FAILED`` - The request to peform a batch prediction did not run to completion. It is not usable.
       
      * ``COMPLETED`` - The batch prediction process completed successfully.
       
      * ``DELETED`` - The ``BatchPrediction`` is marked as deleted. It is not usable.
       

      

      

    OutputUri -> (string)

      

      The location of an Amazon S3 bucket or directory to receive the operation results. The following substrings are not allowed in the s3 key portion of the "outputURI" field: ':', '//', '/./', '/../'.

      

      

    Message -> (string)

      

      A description of the most recent details about processing the batch prediction request.

      

      

    

  

NextToken -> (string)

  

  The ID of the next page in the paginated results that indicates at least one more page follows.

  

  

