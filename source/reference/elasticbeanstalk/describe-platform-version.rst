[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-platform-version:


*************************
describe-platform-version
*************************



===========
Description
===========



Describes the version of the platform.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DescribePlatformVersion>`_


========
Synopsis
========

::

    describe-platform-version
  [--platform-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--platform-arn`` (string)


  The ARN of the version of the platform.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PlatformDescription -> (structure)

  

  Detailed information about the version of the platform.

  

  PlatformArn -> (string)

    

    The ARN of the platform.

    

    

  PlatformOwner -> (string)

    

    The AWS account ID of the person who created the platform.

    

    

  PlatformName -> (string)

    

    The name of the platform.

    

    

  PlatformVersion -> (string)

    

    The version of the platform.

    

    

  SolutionStackName -> (string)

    

    The name of the solution stack used by the platform.

    

    

  PlatformStatus -> (string)

    

    The status of the platform.

    

    

  DateCreated -> (timestamp)

    

    The date when the platform was created.

    

    

  DateUpdated -> (timestamp)

    

    The date when the platform was last updated.

    

    

  PlatformCategory -> (string)

    

    The category of the platform.

    

    

  Description -> (string)

    

    The description of the platform.

    

    

  Maintainer -> (string)

    

    Information about the maintainer of the platform.

    

    

  OperatingSystemName -> (string)

    

    The operating system used by the platform.

    

    

  OperatingSystemVersion -> (string)

    

    The version of the operating system used by the platform.

    

    

  ProgrammingLanguages -> (list)

    

    The programming languages supported by the platform.

    

    (structure)

      

      A programming language supported by the platform.

      

      Name -> (string)

        

        The name of the programming language.

        

        

      Version -> (string)

        

        The version of the programming language.

        

        

      

    

  Frameworks -> (list)

    

    The frameworks supported by the platform.

    

    (structure)

      

      A framework supported by the custom platform.

      

      Name -> (string)

        

        The name of the framework.

        

        

      Version -> (string)

        

        The version of the framework.

        

        

      

    

  CustomAmiList -> (list)

    

    The custom AMIs supported by the platform.

    

    (structure)

      

      A custom AMI available to platforms.

      

      VirtualizationType -> (string)

        

        The type of virtualization used to create the custom AMI.

        

        

      ImageId -> (string)

        

        THe ID of the image used to create the custom AMI.

        

        

      

    

  SupportedTierList -> (list)

    

    The tiers supported by the platform.

    

    (string)

      

      

    

  SupportedAddonList -> (list)

    

    The additions supported by the platform.

    

    (string)

      

      

    

  

