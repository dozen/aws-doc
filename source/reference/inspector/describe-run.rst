[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-run:


************
describe-run
************



===========
Description
===========



Describes the assessment run specified by the run ARN.



========
Synopsis
========

::

    describe-run
  --run-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--run-arn`` (string)


  The ARN specifying the assessment run that you want to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

run -> (structure)

  

  Information about the assessment run.

  

  runArn -> (string)

    

    The ARN of the run.

    

    

  runName -> (string)

    

    The auto-generated name for the run. 

    

    

  assessmentArn -> (string)

    

    The ARN of the assessment that is associated with the run.

    

    

  runState -> (string)

    

    The state of the run. Values can be set to *DataCollectionComplete* , *EvaluatingPolicies* , *EvaluatingPoliciesErrorCanRetry* , *Completed* , *Failed* , *TombStoned* .

    

    

  rulesPackages -> (list)

    

    Rules packages selected for the run of the assessment.

    

    (string)

      

      

    

  creationTime -> (timestamp)

    

    Run creation time that corresponds to the data collection completion time or failure.

    

    

  completionTime -> (timestamp)

    

    Run completion time that corresponds to the rules packages evaluation completion time or failure.

    

    

  

