[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector get-assessment-telemetry:


************************
get-assessment-telemetry
************************



===========
Description
===========



Returns the metadata about the telemetry (application behavioral data) for the assessment specified by the assessment ARN.



========
Synopsis
========

::

    get-assessment-telemetry
  --assessment-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assessment-arn`` (string)


  The ARN specifying the assessment the telemetry of which you want to obtain.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

telemetry -> (list)

  

  Telemetry details.

  

  (structure)

    

    The metadata about the Inspector application data metrics collected by the agent.

     

    This data type is used as the response element in the  get-assessment-telemetry action.

    

    status -> (string)

      

      The category of the individual metrics that together constitute the telemetry that Inspector received from the agent.

      

      

    messageTypeTelemetries -> (list)

      

      Counts of individual metrics received by Inspector from the agent.

      

      (structure)

        

        This data type is used in the  Telemetry data type.

         

        This is metadata about the behavioral data collected by the Inspector agent on your EC2 instances during an assessment and passed to the Inspector service for analysis. 

        

        messageType -> (string)

          

          A specific type of behavioral data that is collected by the agent.

          

          

        count -> (long)

          

          The number of times that the behavioral data is collected by the agent during an assessment.

          

          

        dataSize -> (long)

          

          The total size of the behavioral data that is collected by the agent during an assessment.

          

          

        

      

    

  

