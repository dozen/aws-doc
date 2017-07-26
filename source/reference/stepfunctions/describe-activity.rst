[ :ref:`aws <cli:aws>` . :ref:`stepfunctions <cli:aws stepfunctions>` ]

.. _cli:aws stepfunctions describe-activity:


*****************
describe-activity
*****************



===========
Description
===========



Describes an activity.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/states-2016-11-23/DescribeActivity>`_


========
Synopsis
========

::

    describe-activity
  --activity-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--activity-arn`` (string)


  The Amazon Resource Name (ARN) of the activity to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

activityArn -> (string)

  

  The Amazon Resource Name (ARN) that identifies the activity.

  

  

name -> (string)

  

  The name of the activity.

  

  

creationDate -> (timestamp)

  

  The date the activity was created.

  

  

