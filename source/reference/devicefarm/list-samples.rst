[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-samples:


************
list-samples
************



===========
Description
===========



Gets information about samples, given an AWS Device Farm project ARN



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/ListSamples>`_


``list-samples`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``samples``


========
Synopsis
========

::

    list-samples
  --arn <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The Amazon Resource Name (ARN) of the project for which you want to list samples.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

samples -> (list)

  

  Information about the samples.

  

  (structure)

    

    Represents a sample of performance data.

    

    arn -> (string)

      

      The sample's ARN.

      

      

    type -> (string)

      

      The sample's type.

       

      Must be one of the following values:

       

       
      * CPU: A CPU sample type. This is expressed as the app processing CPU time (including child processes) as reported by process, as a percentage. 
       
      * MEMORY: A memory usage sample type. This is expressed as the total proportional set size of an app process, in kilobytes. 
       
      * NATIVE_AVG_DRAWTIME 
       
      * NATIVE_FPS 
       
      * NATIVE_FRAMES 
       
      * NATIVE_MAX_DRAWTIME 
       
      * NATIVE_MIN_DRAWTIME 
       
      * OPENGL_AVG_DRAWTIME 
       
      * OPENGL_FPS 
       
      * OPENGL_FRAMES 
       
      * OPENGL_MAX_DRAWTIME 
       
      * OPENGL_MIN_DRAWTIME 
       
      * RX 
       
      * RX_RATE: The total number of bytes per second (TCP and UDP) that are sent, by app process. 
       
      * THREADS: A threads sample type. This is expressed as the total number of threads per app process. 
       
      * TX 
       
      * TX_RATE: The total number of bytes per second (TCP and UDP) that are received, by app process. 
       

      

      

    url -> (string)

      

      The pre-signed Amazon S3 URL that can be used with a corresponding GET request to download the sample's file.

      

      

    

  

nextToken -> (string)

  

  If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

  

  

