[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning describe-ml-models:


******************
describe-ml-models
******************



===========
Description
===========



Returns a list of ``MLModel`` that match the search criteria in the request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/DescribeMLModels>`_


``describe-ml-models`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Results``


========
Synopsis
========

::

    describe-ml-models
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


  Use one of the following variables to filter a list of ``MLModel`` :

   

   
  * ``CreatedAt`` - Sets the search criteria to ``MLModel`` creation date.
   
  * ``Status`` - Sets the search criteria to ``MLModel`` status.
   
  * ``Name`` - Sets the search criteria to the contents of ``MLModel`` ****  ``Name`` .
   
  * ``IAMUser`` - Sets the search criteria to the user account that invoked the ``MLModel`` creation.
   
  * ``TrainingDataSourceId`` - Sets the search criteria to the ``DataSource`` used to train one or more ``MLModel`` .
   
  * ``RealtimeEndpointStatus`` - Sets the search criteria to the ``MLModel`` real-time endpoint status.
   
  * ``MLModelType`` - Sets the search criteria to ``MLModel`` type: binary, regression, or multi-class.
   
  * ``Algorithm`` - Sets the search criteria to the algorithm that the ``MLModel`` uses.
   
  * ``TrainingDataURI`` - Sets the search criteria to the data file(s) used in training a ``MLModel`` . The URL can identify either a file or an Amazon Simple Storage Service (Amazon S3) bucket or directory.
   

  

  Possible values:

  
  *   ``CreatedAt``

  
  *   ``LastUpdatedAt``

  
  *   ``Status``

  
  *   ``Name``

  
  *   ``IAMUser``

  
  *   ``TrainingDataSourceId``

  
  *   ``RealtimeEndpointStatus``

  
  *   ``MLModelType``

  
  *   ``Algorithm``

  
  *   ``TrainingDataURI``

  

  

``--eq`` (string)


  The equal to operator. The ``MLModel`` results will have ``FilterVariable`` values that exactly match the value specified with ``EQ`` .

  

``--gt`` (string)


  The greater than operator. The ``MLModel`` results will have ``FilterVariable`` values that are greater than the value specified with ``GT`` .

  

``--lt`` (string)


  The less than operator. The ``MLModel`` results will have ``FilterVariable`` values that are less than the value specified with ``LT`` .

  

``--ge`` (string)


  The greater than or equal to operator. The ``MLModel`` results will have ``FilterVariable`` values that are greater than or equal to the value specified with ``GE`` . 

  

``--le`` (string)


  The less than or equal to operator. The ``MLModel`` results will have ``FilterVariable`` values that are less than or equal to the value specified with ``LE`` .

  

``--ne`` (string)


  The not equal to operator. The ``MLModel`` results will have ``FilterVariable`` values not equal to the value specified with ``NE`` .

  

``--prefix`` (string)


  A string that is found at the beginning of a variable, such as ``Name`` or ``Id`` .

   

  For example, an ``MLModel`` could have the ``Name``  ``2014-09-09-HolidayGiftMailer`` . To search for this ``MLModel`` , select ``Name`` for the ``FilterVariable`` and any of the following strings for the ``Prefix`` : 

   

   
  * 2014-09
   
  * 2014-09-09
   
  * 2014-09-09-Holiday
   

  

``--sort-order`` (string)


  A two-value parameter that determines the sequence of the resulting list of ``MLModel`` .

   

   
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

  

  A list of ``MLModel`` that meet the search criteria.

  

  (structure)

    

    Represents the output of a ``get-ml-model`` operation. 

     

    The content consists of the detailed metadata and the current status of the ``MLModel`` .

    

    MLModelId -> (string)

      

      The ID assigned to the ``MLModel`` at creation.

      

      

    TrainingDataSourceId -> (string)

      

      The ID of the training ``DataSource`` . The ``create-ml-model`` operation uses the ``TrainingDataSourceId`` .

      

      

    CreatedByIamUser -> (string)

      

      The AWS user account from which the ``MLModel`` was created. The account type can be either an AWS root account or an AWS Identity and Access Management (IAM) user account.

      

      

    CreatedAt -> (timestamp)

      

      The time that the ``MLModel`` was created. The time is expressed in epoch time.

      

      

    LastUpdatedAt -> (timestamp)

      

      The time of the most recent edit to the ``MLModel`` . The time is expressed in epoch time.

      

      

    Name -> (string)

      

      A user-supplied name or description of the ``MLModel`` .

      

      

    Status -> (string)

      

      The current status of an ``MLModel`` . This element can have one of the following values: 

       

       
      * ``PENDING`` - Amazon Machine Learning (Amazon ML) submitted a request to create an ``MLModel`` .
       
      * ``INPROGRESS`` - The creation process is underway.
       
      * ``FAILED`` - The request to create an ``MLModel`` didn't run to completion. The model isn't usable.
       
      * ``COMPLETED`` - The creation process completed successfully.
       
      * ``DELETED`` - The ``MLModel`` is marked as deleted. It isn't usable.
       

      

      

    SizeInBytes -> (long)

      

      Long integer type that is a 64-bit signed number.

      

      

    EndpointInfo -> (structure)

      

      The current endpoint of the ``MLModel`` .

      

      PeakRequestsPerSecond -> (integer)

        

        The maximum processing rate for the real-time endpoint for ``MLModel`` , measured in incoming requests per second.

        

        

      CreatedAt -> (timestamp)

        

        The time that the request to create the real-time endpoint for the ``MLModel`` was received. The time is expressed in epoch time.

        

        

      EndpointUrl -> (string)

        

        The URI that specifies where to send real-time prediction requests for the ``MLModel`` .

         

        .. note::

          Note 

          The application must wait until the real-time endpoint is ready before using this URI.

           

        

        

      EndpointStatus -> (string)

        

        The current status of the real-time endpoint for the ``MLModel`` . This element can have one of the following values: 

         

         
        * ``NONE`` - Endpoint does not exist or was previously deleted.
         
        * ``READY`` - Endpoint is ready to be used for real-time predictions.
         
        * ``UPDATING`` - Updating/creating the endpoint. 
         

        

        

      

    TrainingParameters -> (map)

      

      A list of the training parameters in the ``MLModel`` . The list is implemented as a map of key-value pairs.

       

      The following is the current set of training parameters: 

       

       
      * ``sgd.maxMLModelSizeInBytes`` - The maximum allowed size of the model. Depending on the input data, the size of the model might affect its performance. The value is an integer that ranges from ``100000`` to ``2147483648`` . The default value is ``33554432`` . 
       
      * ``sgd.maxPasses`` - The number of times that the training process traverses the observations to build the ``MLModel`` . The value is an integer that ranges from ``1`` to ``10000`` . The default value is ``10`` .
       
      * ``sgd.shuffleType`` - Whether Amazon ML shuffles the training data. Shuffling the data improves a model's ability to find the optimal solution for a variety of data types. The valid values are ``auto`` and ``none`` . The default value is ``none`` .
       
      * ``sgd.l1RegularizationAmount`` - The coefficient regularization L1 norm, which controls overfitting the data by penalizing large coefficients. This parameter tends to drive coefficients to zero, resulting in sparse feature set. If you use this parameter, start by specifying a small value, such as ``1.0E-08`` . The value is a double that ranges from ``0`` to ``MAX_DOUBLE`` . The default is to not use L1 normalization. This parameter can't be used when ``L2`` is specified. Use this parameter sparingly. 
       
      * ``sgd.l2RegularizationAmount`` - The coefficient regularization L2 norm, which controls overfitting the data by penalizing large coefficients. This tends to drive coefficients to small, nonzero values. If you use this parameter, start by specifying a small value, such as ``1.0E-08`` . The value is a double that ranges from ``0`` to ``MAX_DOUBLE`` . The default is to not use L2 normalization. This parameter can't be used when ``L1`` is specified. Use this parameter sparingly. 
       

      

      key -> (string)

        

        String type.

        

        

      value -> (string)

        

        String type.

        

        

      

    InputDataLocationS3 -> (string)

      

      The location of the data file or directory in Amazon Simple Storage Service (Amazon S3).

      

      

    Algorithm -> (string)

      

      The algorithm used to train the ``MLModel`` . The following algorithm is supported:

       

       
      * ``SGD`` -- Stochastic gradient descent. The goal of ``SGD`` is to minimize the gradient of the loss function. 
       

      

      

    MLModelType -> (string)

      

      Identifies the ``MLModel`` category. The following are the available types:

       

       
      * ``REGRESSION`` - Produces a numeric result. For example, "What price should a house be listed at?"
       
      * ``BINARY`` - Produces one of two possible results. For example, "Is this a child-friendly web site?".
       
      * ``MULTICLASS`` - Produces one of several possible results. For example, "Is this a HIGH-, LOW-, or MEDIUM-risk trade?".
       

      

      

    ScoreThreshold -> (float)

      

      

    ScoreThresholdLastUpdatedAt -> (timestamp)

      

      The time of the most recent edit to the ``ScoreThreshold`` . The time is expressed in epoch time.

      

      

    Message -> (string)

      

      A description of the most recent details about accessing the ``MLModel`` .

      

      

    ComputeTime -> (long)

      

      Long integer type that is a 64-bit signed number.

      

      

    FinishedAt -> (timestamp)

      

      A timestamp represented in epoch time.

      

      

    StartedAt -> (timestamp)

      

      A timestamp represented in epoch time.

      

      

    

  

NextToken -> (string)

  

  The ID of the next page in the paginated results that indicates at least one more page follows.

  

  

