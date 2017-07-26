[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift delete-build:


************
delete-build
************



===========
Description
===========



Deletes a build. This action permanently deletes the build record and any uploaded build files.

 

To delete a build, specify its ID. Deleting a build does not affect the status of any active fleets, but you can no longer create new fleets for the deleted build.



========
Synopsis
========

::

    delete-build
  --build-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--build-id`` (string)


  Unique identifier for the build you want to delete. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None