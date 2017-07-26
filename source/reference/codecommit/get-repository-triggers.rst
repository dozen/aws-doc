[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit get-repository-triggers:


***********************
get-repository-triggers
***********************



===========
Description
===========



Gets information about triggers configured for a repository.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/GetRepositoryTriggers>`_


========
Synopsis
========

::

    get-repository-triggers
  --repository-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository for which the trigger is configured.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

configurationId -> (string)

  

  The system-generated unique ID for the trigger.

  

  

triggers -> (list)

  

  The JSON block of configuration information for each trigger.

  

  (structure)

    

    Information about a trigger for a repository.

    

    name -> (string)

      

      The name of the trigger.

      

      

    destinationArn -> (string)

      

      The ARN of the resource that is the target for a trigger. For example, the ARN of a topic in Amazon Simple Notification Service (SNS).

      

      

    customData -> (string)

      

      Any custom data associated with the trigger that will be included in the information sent to the target of the trigger.

      

      

    branches -> (list)

      

      The branches that will be included in the trigger configuration. If no branches are specified, the trigger will apply to all branches.

      

      (string)

        

        

      

    events -> (list)

      

      The repository events that will cause the trigger to run actions in another service, such as sending a notification through Amazon Simple Notification Service (SNS). 

       

      .. note::

         

        The valid value "all" cannot be used with any other values.

         

      

      (string)

        

        

      

    

  

