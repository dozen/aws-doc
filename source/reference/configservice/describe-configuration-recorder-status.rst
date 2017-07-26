[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice describe-configuration-recorder-status:


**************************************
describe-configuration-recorder-status
**************************************



===========
Description
===========



Returns the current status of the specified configuration recorder. If a configuration recorder is not specified, this action returns the status of all configuration recorder associated with the account.

 

.. note::

  Currently, you can specify only one configuration recorder per account.



========
Synopsis
========

::

    describe-configuration-recorder-status
  [--configuration-recorder-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--configuration-recorder-names`` (list)


  The name(s) of the configuration recorder. If the name is not specified, the action returns the current status of all the configuration recorders associated with the account. 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get status information for the configuration recorder**

The following command returns the status of the default configuration recorder::

    aws configservice describe-configuration-recorder-status

Output::

    {
        "ConfigurationRecordersStatus": [
            {
                "name": "default",
                "lastStatus": "SUCCESS",
                "recording": true,
                "lastStatusChangeTime": 1452193834.344,
                "lastStartTime": 1441039997.819,
                "lastStopTime": 1441039992.835
            }
        ]
    }

======
Output
======

ConfigurationRecordersStatus -> (list)

  

  A list that contains status of the specified recorders. 

  

  (structure)

    

    The current status of the configuration recorder.

    

    name -> (string)

      

      The name of the configuration recorder.

      

      

    lastStartTime -> (timestamp)

      

      The time the recorder was last started.

      

      

    lastStopTime -> (timestamp)

      

      The time the recorder was last stopped.

      

      

    recording -> (boolean)

      

      Specifies whether the recorder is currently recording or not.

      

      

    lastStatus -> (string)

      

      The last (previous) status of the recorder.

      

      

    lastErrorCode -> (string)

      

      The error code indicating that the recording failed.

      

      

    lastErrorMessage -> (string)

      

      The message indicating that the recording failed due to an error.

      

      

    lastStatusChangeTime -> (timestamp)

      

      The time when the status was last changed.

      

      

    

  

