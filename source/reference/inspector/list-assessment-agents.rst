[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-assessment-agents:


**********************
list-assessment-agents
**********************



===========
Description
===========



Lists the agents of the assessment specified by the assessment ARN.



========
Synopsis
========

::

    list-assessment-agents
  --assessment-arn <value>
  [--filter <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assessment-arn`` (string)


  The ARN specifying the assessment whose agents you want to list.

  

``--filter`` (structure)


  You can use this parameter to specify a subset of data to be included in the action's response.

   

  For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

  



Shorthand Syntax::

    agentHealthList=string,string




JSON Syntax::

  {
    "agentHealthList": ["string", ...]
  }



``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to 'null' on your first call to the **list-assessment-agents** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

agentList -> (list)

  

  A list of ARNs specifying the agents returned by the action.

  

  (structure)

    

    Contains information about an Inspector agent. This data type is used as a response element in the  list-assessment-agents action.

    

    agentId -> (string)

      

      The EC2 instance ID where the agent is installed.

      

      

    assessmentArn -> (string)

      

      The ARN of the assessment that is associated with the agent.

      

      

    agentHealth -> (string)

      

      The current health state of the agent. Values can be set to *HEALTHY* or *UNHEALTHY* .

      

      

    agentHealthCode -> (string)

      

      The detailed health state of the agent. Values can be set to *RUNNING* , *HEALTHY* , *UNHEALTHY* , *UNKNOWN* , *BLACKLISTED* , *SHUTDOWN* , *THROTTLED* . 

      

      

    agentHealthDetails -> (string)

      

      The description for the agent health code.

      

      

    autoScalingGroup -> (string)

      

      This data type property is currently not used.

      

      

    accountId -> (string)

      

      AWS account of the EC2 instance where the agent is installed.

      

      

    telemetry -> (list)

      

      The Inspector application data metrics collected by the agent. 

      

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

              

              

            

          

        

      

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to 'null'.

  

  

