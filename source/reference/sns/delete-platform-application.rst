[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns delete-platform-application:


***************************
delete-platform-application
***************************



===========
Description
===========



Deletes a platform application object for one of the supported push notification services, such as APNS and GCM. For more information, see `Using Amazon SNS Mobile Push Notifications <http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/DeletePlatformApplication>`_


========
Synopsis
========

::

    delete-platform-application
  --platform-application-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--platform-application-arn`` (string)


  PlatformApplicationArn of platform application object to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None