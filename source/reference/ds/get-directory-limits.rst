[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds get-directory-limits:


********************
get-directory-limits
********************



===========
Description
===========



Obtains directory limit information for the current region.



========
Synopsis
========

::

    get-directory-limits
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DirectoryLimits -> (structure)

  

  A  DirectoryLimits object that contains the directory limits for the current region.

  

  CloudOnlyDirectoriesLimit -> (integer)

    

    The maximum number of cloud directories allowed in the region.

    

    

  CloudOnlyDirectoriesCurrentCount -> (integer)

    

    The current number of cloud directories in the region.

    

    

  CloudOnlyDirectoriesLimitReached -> (boolean)

    

    Indicates if the cloud directory limit has been reached.

    

    

  CloudOnlyMicrosoftADLimit -> (integer)

    The maximum number of Microsoft AD directories allowed in the region.

    

  CloudOnlyMicrosoftADCurrentCount -> (integer)

    The current number of Microsoft AD directories in the region.

    

  CloudOnlyMicrosoftADLimitReached -> (boolean)

    Indicates if the Microsoft AD directory limit has been reached.

    

  ConnectedDirectoriesLimit -> (integer)

    

    The maximum number of connected directories allowed in the region.

    

    

  ConnectedDirectoriesCurrentCount -> (integer)

    

    The current number of connected directories in the region.

    

    

  ConnectedDirectoriesLimitReached -> (boolean)

    

    Indicates if the connected directory limit has been reached.

    

    

  

