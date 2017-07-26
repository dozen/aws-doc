[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk delete-platform-version:


***********************
delete-platform-version
***********************



===========
Description
===========



Deletes the specified version of a custom platform.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DeletePlatformVersion>`_


========
Synopsis
========

::

    delete-platform-version
  [--platform-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--platform-arn`` (string)


  The ARN of the version of the custom platform.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PlatformSummary -> (structure)

  

  Detailed information about the version of the custom platform.

  

  PlatformArn -> (string)

    

    The ARN of the platform.

    

    

  PlatformOwner -> (string)

    

    The AWS account ID of the person who created the platform.

    

    

  PlatformStatus -> (string)

    

    The status of the platform. You can create an environment from the platform once it is ready.

    

    

  PlatformCategory -> (string)

    

    The category of platform.

    

    

  OperatingSystemName -> (string)

    

    The operating system used by the platform.

    

    

  OperatingSystemVersion -> (string)

    

    The version of the operating system used by the platform.

    

    

  SupportedTierList -> (list)

    

    The tiers in which the platform runs.

    

    (string)

      

      

    

  SupportedAddonList -> (list)

    

    The additions associated with the platform.

    

    (string)

      

      

    

  

