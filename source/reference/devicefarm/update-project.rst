[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm update-project:


**************
update-project
**************



===========
Description
===========



Modifies the specified project name, given the project ARN and a new name.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/UpdateProject>`_


========
Synopsis
========

::

    update-project
  --arn <value>
  [--name <value>]
  [--default-job-timeout-minutes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The Amazon Resource name (ARN) of the project whose name you wish to update.

  

``--name`` (string)


  A string representing the new name of the project that you are updating.

  

``--default-job-timeout-minutes`` (integer)


  The number of minutes a test run in the project will execute before it times out.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

project -> (structure)

  

  The project you wish to update.

  

  arn -> (string)

    

    The project's ARN.

    

    

  name -> (string)

    

    The project's name.

    

    

  defaultJobTimeoutMinutes -> (integer)

    

    The default number of minutes (at the project level) a test run will execute before it times out. Default value is 60 minutes.

    

    

  created -> (timestamp)

    

    When the project was created.

    

    

  

