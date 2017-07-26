[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` . :ref:`wait <cli:aws machinelearning wait>` ]

.. _cli:aws machinelearning wait evaluation-available:


********************
evaluation-available
********************



===========
Description
===========

Wait until JMESPath query Results[].Status returns COMPLETED for all elements when polling with ``describe-evaluations``. It will poll every 30 seconds until a successful state has been reached. This will exit with a return code of 255 after 60 failed checks.

``evaluation-available`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Results``


========
Synopsis
========

::

    evaluation-available
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

None