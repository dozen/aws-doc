[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm update-project:


**************
update-project
**************



===========
Description
===========



Modifies the specified project name, given the project ARN and a new name.



========
Synopsis
========

::

    update-project
  --arn <value>
  [--name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--arn`` (string)


  The Amazon Resource name (ARN) of the project whose name you wish to update.

  

``--name`` (string)


  A string representing the new name of the project that you are updating.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

project -> (structure)

  

  Represents an operating-system neutral workspace for running and managing tests.

  

  arn -> (string)

    

    The project's ARN.

    

    

  name -> (string)

    

    The project's name.

    

    

  created -> (timestamp)

    

    When the project was created.

    

    

  

