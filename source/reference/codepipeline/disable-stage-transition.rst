[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline disable-stage-transition:


************************
disable-stage-transition
************************



===========
Description
===========



Prevents artifacts in a pipeline from transitioning to the next stage in the pipeline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/DisableStageTransition>`_


========
Synopsis
========

::

    disable-stage-transition
  --pipeline-name <value>
  --stage-name <value>
  --transition-type <value>
  --reason <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-name`` (string)


  The name of the pipeline in which you want to disable the flow of artifacts from one stage to another.

  

``--stage-name`` (string)


  The name of the stage where you want to disable the inbound or outbound transition of artifacts.

  

``--transition-type`` (string)


  Specifies whether artifacts will be prevented from transitioning into the stage and being processed by the actions in that stage (inbound), or prevented from transitioning from the stage after they have been processed by the actions in that stage (outbound).

  

  Possible values:

  
  *   ``Inbound``

  
  *   ``Outbound``

  

  

``--reason`` (string)


  The reason given to the user why a stage is disabled, such as waiting for manual approval or manual tests. This message is displayed in the pipeline console UI.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To disable a transition to a stage in a pipeline**

This example disables transitions into the Beta stage of the MyFirstPipeline pipeline in AWS CodePipeline. 

Command::

  aws codepipeline disable-stage-transition --pipeline-name MyFirstPipeline --stage-name Beta  --transition-type Inbound


Output::

  None.

======
Output
======

None