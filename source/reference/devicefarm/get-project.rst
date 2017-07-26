[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-project:


***********
get-project
***********



===========
Description
===========



Gets information about a project.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/GetProject>`_


========
Synopsis
========

::

    get-project
  --arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The project's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

project -> (structure)

  

  The project you wish to get information about.

  

  arn -> (string)

    

    The project's ARN.

    

    

  name -> (string)

    

    The project's name.

    

    

  defaultJobTimeoutMinutes -> (integer)

    

    The default number of minutes (at the project level) a test run will execute before it times out. Default value is 60 minutes.

    

    

  created -> (timestamp)

    

    When the project was created.

    

    

  

