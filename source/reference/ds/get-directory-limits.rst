[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds get-directory-limits:


********************
get-directory-limits
********************



===========
Description
===========



Obtains directory limit information for the current region.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/GetDirectoryLimits>`_


========
Synopsis
========

::

    get-directory-limits
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    

  

