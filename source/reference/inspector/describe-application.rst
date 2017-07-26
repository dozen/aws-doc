[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-application:


********************
describe-application
********************



===========
Description
===========



Describes the application specified by the application ARN.



========
Synopsis
========

::

    describe-application
  --application-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-arn`` (string)


  The ARN specifying the application that you want to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

application -> (structure)

  

  Information about the application.

  

  applicationArn -> (string)

    

    The ARN specifying the Inspector application. 

    

    

  applicationName -> (string)

    

    The name of the Inspector application. 

    

    

  resourceGroupArn -> (string)

    

    The ARN specifying the resource group that is associated with the application. 

    

    

  

