[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns delete-platform-application:


***************************
delete-platform-application
***************************



===========
Description
===========



Deletes a platform application object for one of the supported push notification services, such as APNS and GCM. For more information, see `Using Amazon SNS Mobile Push Notifications`_ . 



========
Synopsis
========

::

    delete-platform-application
  --platform-application-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--platform-application-arn`` (string)


  PlatformApplicationArn of platform application object to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Using Amazon SNS Mobile Push Notifications: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html
