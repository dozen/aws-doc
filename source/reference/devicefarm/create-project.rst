[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm create-project:


**************
create-project
**************



===========
Description
===========



Creates a new project.



========
Synopsis
========

::

    create-project
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The project's name.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

project -> (structure)

  

  The newly created project.

  

  arn -> (string)

    

    The project's ARN.

    

    

  name -> (string)

    

    The project's name.

    

    

  created -> (timestamp)

    

    When the project was created.

    

    

  

