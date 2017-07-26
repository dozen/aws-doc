[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline enable-stage-transition:


***********************
enable-stage-transition
***********************



===========
Description
===========



Enables artifacts in a pipeline to transition to a stage in a pipeline.



========
Synopsis
========

::

    enable-stage-transition
  --pipeline-name <value>
  --stage-name <value>
  --transition-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--pipeline-name`` (string)


  The name of the pipeline in which you want to enable the flow of artifacts from one stage to another.

  

``--stage-name`` (string)


  The name of the stage where you want to enable the transition of artifacts, either into the stage (inbound) or from that stage to the next stage (outbound).

  

``--transition-type`` (string)


  Specifies whether artifacts will be allowed to enter the stage and be processed by the actions in that stage (inbound) or whether already-processed artifacts will be allowed to transition to the next stage (outbound).

  

  Possible values:

  
  *   ``Inbound``

  
  *   ``Outbound``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To enable a transition to a stage in a pipeline**

This example enables transitions into the Beta stage of the MyFirstPipeline pipeline in AWS CodePipeline. 

Command::

  aws codepipeline enable-stage-transition --pipeline-name MyFirstPipeline --stage-name Beta  --transition-type Inbound


Output::

  None.

======
Output
======

None