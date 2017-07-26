[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-projects:


*************
list-projects
*************



===========
Description
===========



Gets information about projects.



========
Synopsis
========

::

    list-projects
  [--arn <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--arn`` (string)


  The projects' ARNs.

  

``--next-token`` (string)


  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

projects -> (list)

  

  Information about the projects.

  

  (structure)

    

    Represents an operating-system neutral workspace for running and managing tests.

    

    arn -> (string)

      

      The project's ARN.

      

      

    name -> (string)

      

      The project's name.

      

      

    created -> (timestamp)

      

      When the project was created.

      

      

    

  

nextToken -> (string)

  

  If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

  

  

