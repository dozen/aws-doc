[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-samples:


************
list-samples
************



===========
Description
===========



Gets information about samples.



========
Synopsis
========

::

    list-samples
  --arn <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--arn`` (string)


  The samples' ARNs.

  

``--next-token`` (string)


  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  

