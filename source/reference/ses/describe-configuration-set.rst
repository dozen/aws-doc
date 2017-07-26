[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses describe-configuration-set:


**************************
describe-configuration-set
**************************



===========
Description
===========



Returns the details of the specified configuration set.

 

Configuration sets enable you to publish email sending events. For information about using configuration sets, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/monitor-sending-activity.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/DescribeConfigurationSet>`_


========
Synopsis
========

::

    describe-configuration-set
  --configuration-set-name <value>
  [--configuration-set-attribute-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-set-name`` (string)


  The name of the configuration set to describe.

  

``--configuration-set-attribute-names`` (list)


  A list of configuration set attributes to return.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    eventDestinations





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ConfigurationSet -> (structure)

  

  The configuration set object associated with the specified configuration set.

  

  Name -> (string)

    

    The name of the configuration set. The name must:

     

     
    * Contain only ASCII letters (a-z, A-Z), numbers (0-9), underscores (_), or dashes (-). 
     
    * Contain less than 64 characters. 
     

    

    

  

EventDestinations -> (list)

  

  A list of event destinations associated with the configuration set. 

  

  (structure)

    

    Contains information about the event destination to which the specified email sending events are published.

     

    .. note::

       

      When you create or update an event destination, you must provide one, and only one, destination. The destination can be either Amazon CloudWatch or Amazon Kinesis Firehose.

       

     

    Event destinations are associated with configuration sets, which enable you to publish email sending events to Amazon CloudWatch or Amazon Kinesis Firehose. For information about using configuration sets, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/monitor-sending-activity.html>`_ .

    

    Name -> (string)

      

      The name of the event destination. The name must:

       

       
      * Contain only ASCII letters (a-z, A-Z), numbers (0-9), underscores (_), or dashes (-). 
       
      * Contain less than 64 characters. 
       

      

      

    Enabled -> (boolean)

      

      Sets whether Amazon SES publishes events to this destination when you send an email with the associated configuration set. Set to ``true`` to enable publishing to this destination; set to ``false`` to prevent publishing to this destination. The default value is ``false`` .

      

      

    MatchingEventTypes -> (list)

      

      The type of email sending events to publish to the event destination.

      

      (string)

        

        

      

    KinesisFirehoseDestination -> (structure)

      

      An object that contains the delivery stream ARN and the IAM role ARN associated with an Amazon Kinesis Firehose event destination.

      

      IAMRoleARN -> (string)

        

        The ARN of the IAM role under which Amazon SES publishes email sending events to the Amazon Kinesis Firehose stream.

        

        

      DeliveryStreamARN -> (string)

        

        The ARN of the Amazon Kinesis Firehose stream to which to publish email sending events.

        

        

      

    CloudWatchDestination -> (structure)

      

      An object that contains the names, default values, and sources of the dimensions associated with an Amazon CloudWatch event destination.

      

      DimensionConfigurations -> (list)

        

        A list of dimensions upon which to categorize your emails when you publish email sending events to Amazon CloudWatch.

        

        (structure)

          

          Contains the dimension configuration to use when you publish email sending events to Amazon CloudWatch.

           

          For information about publishing email sending events to Amazon CloudWatch, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/monitor-sending-activity.html>`_ .

          

          DimensionName -> (string)

            

            The name of an Amazon CloudWatch dimension associated with an email sending metric. The name must:

             

             
            * Contain only ASCII letters (a-z, A-Z), numbers (0-9), underscores (_), or dashes (-). 
             
            * Contain less than 256 characters. 
             

            

            

          DimensionValueSource -> (string)

            

            The place where Amazon SES finds the value of a dimension to publish to Amazon CloudWatch. If you want Amazon SES to use the message tags that you specify using an ``X-SES-MESSAGE-TAGS`` header or a parameter to the ``send-email`` /``send-raw-email`` API, choose ``messageTag`` . If you want Amazon SES to use your own email headers, choose ``emailHeader`` .

            

            

          DefaultDimensionValue -> (string)

            

            The default value of the dimension that is published to Amazon CloudWatch if you do not provide the value of the dimension when you send an email. The default value must:

             

             
            * Contain only ASCII letters (a-z, A-Z), numbers (0-9), underscores (_), or dashes (-). 
             
            * Contain less than 256 characters. 
             

            

            

          

        

      

    

  

