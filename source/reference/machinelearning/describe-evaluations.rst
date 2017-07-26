[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning describe-evaluations:


********************
describe-evaluations
********************



===========
Description
===========



Returns a list of ``describe-evaluations`` that match the search criteria in the request.



``describe-evaluations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Results``


========
Synopsis
========

::

    describe-evaluations
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


  Use one of the following variable to filter a list of ``Evaluation`` objects:

   

   
  * ``CreatedAt`` - Sets the search criteria to the ``Evaluation`` creation date.
   
  * ``Status`` - Sets the search criteria to the ``Evaluation`` status.
   
  * ``Name`` - Sets the search criteria to the contents of ``Evaluation``  ****  ``Name`` .
   
  * ``IAMUser`` - Sets the search criteria to the user account that invoked an ``Evaluation`` .
   
  * ``MLModelId`` - Sets the search criteria to the ``MLModel`` that was evaluated.
   
  * ``DataSourceId`` - Sets the search criteria to the ``DataSource`` used in ``Evaluation`` .
   
  * ``DataUri`` - Sets the search criteria to the data file(s) used in ``Evaluation`` . The URL can identify either a file or an Amazon Simple Storage Solution (Amazon S3) bucket or directory.
   

  

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


  The equal to operator. The ``Evaluation`` results will have ``FilterVariable`` values that exactly match the value specified with ``EQ`` .

  

``--gt`` (string)


  The greater than operator. The ``Evaluation`` results will have ``FilterVariable`` values that are greater than the value specified with ``GT`` .

  

``--lt`` (string)


  The less than operator. The ``Evaluation`` results will have ``FilterVariable`` values that are less than the value specified with ``LT`` .

  

``--ge`` (string)


  The greater than or equal to operator. The ``Evaluation`` results will have ``FilterVariable`` values that are greater than or equal to the value specified with ``GE`` . 

  

``--le`` (string)


  The less than or equal to operator. The ``Evaluation`` results will have ``FilterVariable`` values that are less than or equal to the value specified with ``LE`` .

  

``--ne`` (string)


  The not equal to operator. The ``Evaluation`` results will have ``FilterVariable`` values not equal to the value specified with ``NE`` .

  

``--prefix`` (string)


  A string that is found at the beginning of a variable, such as ``Name`` or ``Id`` .

   

  For example, an ``Evaluation`` could have the ``Name``  ``2014-09-09-HolidayGiftMailer`` . To search for this ``Evaluation`` , select ``Name`` for the ``FilterVariable`` and any of the following strings for the ``Prefix`` : 

   

   
  * 2014-09
   
  * 2014-09-09
   
  * 2014-09-09-Holiday
   

  

``--sort-order`` (string)


  A two-value parameter that determines the sequence of the resulting list of ``Evaluation`` .

   

   
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

  

  A list of  Evaluation that meet the search criteria. 

  

  (structure)

    

    Represents the output of  get-evaluation operation. 

     

    The content consists of the detailed metadata and data file information and the current status of the ``Evaluation`` .

    

    EvaluationId -> (string)

      

      The ID that is assigned to the ``Evaluation`` at creation.

      

      

    MLModelId -> (string)

      

      The ID of the ``MLModel`` that is the focus of the evaluation.

      

      

    EvaluationDataSourceId -> (string)

      

      The ID of the ``DataSource`` that is used to evaluate the ``MLModel`` .

      

      

    InputDataLocationS3 -> (string)

      

      The location and name of the data in Amazon Simple Storage Server (Amazon S3) that is used in the evaluation.

      

      

    CreatedByIamUser -> (string)

      

      The AWS user account that invoked the evaluation. The account type can be either an AWS root account or an AWS Identity and Access Management (IAM) user account.

      

      

    CreatedAt -> (timestamp)

      

      The time that the ``Evaluation`` was created. The time is expressed in epoch time.

      

      

    LastUpdatedAt -> (timestamp)

      

      The time of the most recent edit to the ``Evaluation`` . The time is expressed in epoch time.

      

      

    Name -> (string)

      

      A user-supplied name or description of the ``Evaluation`` . 

      

      

    Status -> (string)

      

      The status of the evaluation. This element can have one of the following values:

       

       
      * ``PENDING`` - Amazon Machine Learning (Amazon ML) submitted a request to evaluate an ``MLModel`` .
       
      * ``INPROGRESS`` - The evaluation is underway.
       
      * ``FAILED`` - The request to evaluate an ``MLModel`` did not run to completion. It is not usable.
       
      * ``COMPLETED`` - The evaluation process completed successfully.
       
      * ``DELETED`` - The ``Evaluation`` is marked as deleted. It is not usable.
       

      

      

    PerformanceMetrics -> (structure)

      

      Measurements of how well the ``MLModel`` performed, using observations referenced by the ``DataSource`` . One of the following metrics is returned, based on the type of the MLModel: 

       

       
      * BinaryAUC: A binary ``MLModel`` uses the Area Under the Curve (AUC) technique to measure performance.  
       
      * RegressionRMSE: A regression ``MLModel`` uses the Root Mean Square Error (RMSE) technique to measure performance. RMSE measures the difference between predicted and actual values for a single variable. 
       
      * MulticlassAvgFScore: A multiclass ``MLModel`` uses the F1 score technique to measure performance.  
       

       

      For more information about performance metrics, please see the `Amazon Machine Learning Developer Guide`_ . 

      

      Properties -> (map)

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      

    Message -> (string)

      

      A description of the most recent details about evaluating the ``MLModel`` .

      

      

    

  

NextToken -> (string)

  

  The ID of the next page in the paginated results that indicates at least one more page follows.

  

  



.. _Amazon Machine Learning Developer Guide: http://docs.aws.amazon.com/machine-learning/latest/dg
