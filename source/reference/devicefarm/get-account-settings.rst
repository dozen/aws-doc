[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-account-settings:


********************
get-account-settings
********************



===========
Description
===========



Returns the number of unmetered iOS and/or unmetered Android devices that have been purchased by the account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/GetAccountSettings>`_


========
Synopsis
========

::

    get-account-settings
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

accountSettings -> (structure)

  

  The account settings.

  

  awsAccountNumber -> (string)

    

    The AWS account number specified in the ``AccountSettings`` container.

    

    

  unmeteredDevices -> (map)

    

    Returns the unmetered devices you have purchased or want to purchase.

    

    key -> (string)

      

      

    value -> (integer)

      

      

    

  unmeteredRemoteAccessDevices -> (map)

    

    Returns the unmetered remote access devices you have purchased or want to purchase.

    

    key -> (string)

      

      

    value -> (integer)

      

      

    

  maxJobTimeoutMinutes -> (integer)

    

    The maximum number of minutes a test run will execute before it times out.

    

    

  trialMinutes -> (structure)

    

    Information about an AWS account's usage of free trial device minutes.

    

    total -> (double)

      

      The total number of free trial minutes that the account started with.

      

      

    remaining -> (double)

      

      The number of free trial minutes remaining in the account.

      

      

    

  maxSlots -> (map)

    

    The maximum number of device slots that the AWS account can purchase. Each maximum is expressed as an ``offering-id:number`` pair, where the ``offering-id`` represents one of the IDs returned by the ``list-offerings`` command.

    

    key -> (string)

      

      

    value -> (integer)

      

      

    

  defaultJobTimeoutMinutes -> (integer)

    

    The default number of minutes (at the account level) a test run will execute before it times out. Default value is 60 minutes.

    

    

  

