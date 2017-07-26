[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-account-settings:


********************
get-account-settings
********************



===========
Description
===========



Returns the number of unmetered iOS and/or unmetered Android devices that have been purchased by the account.



========
Synopsis
========

::

    get-account-settings
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

accountSettings -> (structure)

  

  A container for account-level settings within AWS Device Farm.

  

  awsAccountNumber -> (string)

    

    The AWS account number specified in the ``AccountSettings`` container.

    

    

  unmeteredDevices -> (map)

    

    Returns the unmetered devices you have purchased.

    

    key -> (string)

      

      

    value -> (integer)

      

      

    

  

