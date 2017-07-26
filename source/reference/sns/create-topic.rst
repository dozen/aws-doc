[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns create-topic:


************
create-topic
************



===========
Description
===========



Creates a topic to which notifications can be published. Users can create at most 100,000 topics. For more information, see `http\://aws.amazon.com/sns <http://aws.amazon.com/sns/>`_ . This action is idempotent, so if the requester already owns a topic with the specified name, that topic's ARN is returned without creating a new topic.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/CreateTopic>`_


========
Synopsis
========

::

    create-topic
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the topic you want to create.

   

  Constraints: Topic names must be made up of only uppercase and lowercase ASCII letters, numbers, underscores, and hyphens, and must be between 1 and 256 characters long.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command creates an SNS topic named ``my-topic``::

  aws sns create-topic --name my-topic

Output::

  {
      "ResponseMetadata": {
          "RequestId": "1469e8d7-1642-564e-b85d-a19b4b341f83"
      },
      "TopicArn": "arn:aws:sns:us-west-2:0123456789012:my-topic"
  }

For more information, see `Using the AWS Command Line Interface with Amazon SQS and Amazon SNS`_ in the *AWS Command Line Interface User Guide*.

.. _`Using the AWS Command Line Interface with Amazon SQS and Amazon SNS`: http://docs.aws.amazon.com/cli/latest/userguide/cli-sqs-queue-sns-topic.html



======
Output
======

TopicArn -> (string)

  

  The Amazon Resource Name (ARN) assigned to the created topic.

  

  

