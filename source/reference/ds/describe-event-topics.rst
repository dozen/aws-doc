[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds describe-event-topics:


*********************
describe-event-topics
*********************



===========
Description
===========



Obtains information about which SNS topics receive status messages from the specified directory.

 

If no input parameters are provided, such as directory-id or TopicName, this request describes all of the associations in the account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/DescribeEventTopics>`_


========
Synopsis
========

::

    describe-event-topics
  [--directory-id <value>]
  [--topic-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The Directory ID for which to get the list of associated SNS topics. If this member is null, associations for all Directory IDs are returned.

  

``--topic-names`` (list)


  A list of SNS topic names for which to obtain the information. If this member is null, all associations for the specified Directory ID are returned.

   

  An empty list results in an ``InvalidParameterException`` being thrown.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EventTopics -> (list)

  

  A list of SNS topic names that receive status messages from the specified Directory ID.

  

  (structure)

    

    Information about SNS topic and AWS Directory Service directory associations.

    

    DirectoryId -> (string)

      

      The Directory ID of an AWS Directory Service directory that will publish status messages to an SNS topic.

      

      

    TopicName -> (string)

      

      The name of an AWS SNS topic the receives status messages from the directory.

      

      

    TopicArn -> (string)

      

      The SNS topic ARN (Amazon Resource Name).

      

      

    CreatedDateTime -> (timestamp)

      

      The date and time of when you associated your directory with the SNS topic.

      

      

    Status -> (string)

      

      The topic registration status.

      

      

    

  

