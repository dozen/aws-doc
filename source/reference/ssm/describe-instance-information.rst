[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-instance-information:


*****************************
describe-instance-information
*****************************



===========
Description
===========

Describes one or more of your instances. You can use this to get information about instances like the operating system platform, the SSM agent version, status etc. If you specify one or more instance IDs, it returns information for those instances. If you do not specify instance IDs, it returns information for all your instances. If you specify an instance ID that is not valid or an instance that you do not own, you receive an error.

========
Synopsis
========

::

    describe-instance-information
  [--instance-information-filter-list <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-information-filter-list`` (list)
One or more filters. Use a filter to return a more specific list of instances.



Shorthand Syntax::

    key=string,valueSet=string,string ...




JSON Syntax::

  [
    {
      "key": "InstanceIds"|"AgentVersion"|"PingStatus"|"PlatformTypes",
      "valueSet": ["string", ...]
    }
    ...
  ]



``--max-results`` (integer)
The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

``--next-token`` (string)
The token for the next set of items to return. (You received this token from a previous call.)

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

InstanceInformationList -> (list)

  The instance information list.

  (structure)

    Describes a filter for a specific list of instances.

    InstanceId -> (string)

      The instance ID.

      

    PingStatus -> (string)

      Connection status of the SSM agent.

      

    LastPingDateTime -> (timestamp)

      The date and time when agent last pinged SSM service.

      

    AgentVersion -> (string)

      The version of the SSM agent running on your instance.

      

    IsLatestVersion -> (boolean)

      Indicates whether latest version of the SSM agent is running on your instance.

      

    PlatformType -> (string)

      The operating system platform type.

      

    PlatformName -> (string)

      The name of the operating system platform running on your instance.

      

    PlatformVersion -> (string)

      The version of the OS platform running on your instance.

      

    

  

NextToken -> (string)

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

