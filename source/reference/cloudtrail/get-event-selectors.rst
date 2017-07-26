[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail get-event-selectors:


*******************
get-event-selectors
*******************



===========
Description
===========



Describes the settings for the event selectors that you configured for your trail. The information returned for your event selectors includes the following:

 

 
* The S3 objects that you are logging for data events. 
 
* If your event selector includes management events. 
 
* If your event selector includes read-only events, write-only events, or all.  
 

 

For more information, see `Logging Data and Management Events for Trails <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/logging-management-and-data-events-with-cloudtrail.html>`_ in the *AWS CloudTrail User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudtrail-2013-11-01/GetEventSelectors>`_


========
Synopsis
========

::

    get-event-selectors
  --trail-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--trail-name`` (string)


  Specifies the name of the trail or trail ARN. If you specify a trail name, the string must meet the following requirements:

   

   
  * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-) 
   
  * Start with a letter or number, and end with a letter or number 
   
  * Be between 3 and 128 characters 
   
  * Have no adjacent periods, underscores or dashes. Names like ``my-_namespace`` and ``my--namespace`` are invalid. 
   
  * Not be in IP address format (for example, 192.168.5.4) 
   

   

  If you specify a trail ARN, it must be in the format:

   

   ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view the event selector settings for a trail**

The following ``get-event-selectors`` command returns the settings for ``Trail1``::

  aws cloudtrail get-event-selectors --trail-name Trail1

Output::

  {
    "EventSelectors": [
        {
            "IncludeManagementEvents": true,
            "DataResources": [],
            "ReadWriteType": "All"
        }
    ],
    "TrailARN": "arn:aws:cloudtrail:us-east-1:123456789012:trail/Trail1"
  }


======
Output
======

TrailARN -> (string)

  

  The specified trail ARN that has the event selectors.

  

  

EventSelectors -> (list)

  

  The event selectors that are configured for the trail.

  

  (structure)

    

    Use event selectors to specify whether you want your trail to log management and/or data events. When an event occurs in your account, CloudTrail evaluates the event selector for all trails. For each trail, if the event matches any event selector, the trail processes and logs the event. If the event doesn't match any event selector, the trail doesn't log the event.

     

    You can configure up to five event selectors for a trail.

    

    ReadWriteType -> (string)

      

      Specify if you want your trail to log read-only events, write-only events, or all. For example, the EC2 ``GetConsoleOutput`` is a read-only API operation and ``RunInstances`` is a write-only API operation.

       

      By default, the value is ``All`` .

      

      

    IncludeManagementEvents -> (boolean)

      

      Specify if you want your event selector to include management events for your trail.

       

      For more information, see `Management Events <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/logging-management-and-data-events-with-cloudtrail.html#logging-management-events>`_ in the *AWS CloudTrail User Guide* .

       

      By default, the value is ``true`` .

      

      

    DataResources -> (list)

      

      CloudTrail supports logging only data events for S3 objects. You can specify up to 250 S3 buckets and object prefixes for a trail.

       

      For more information, see `Data Events <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/logging-management-and-data-events-with-cloudtrail.html#logging-data-events>`_ in the *AWS CloudTrail User Guide* .

      

      (structure)

        

        The Amazon S3 objects that you specify in your event selectors for your trail to log data events. Data events are object-level API operations that access S3 objects, such as ``GetObject`` , ``DeleteObject`` , and ``PutObject`` . You can specify up to 250 S3 buckets and object prefixes for a trail. 

         

        Example

         

         
        * You create an event selector for a trail and specify an S3 bucket and an empty prefix, such as ``arn:aws:s3:::bucket-1/`` . 
         
        * You upload an image file to ``bucket-1`` . 
         
        * The ``PutObject`` API operation occurs on an object in the S3 bucket that you specified in the event selector. The trail processes and logs the event. 
         
        * You upload another image file to a different S3 bucket named ``arn:aws:s3:::bucket-2`` . 
         
        * The event occurs on an object in an S3 bucket that you didn't specify in the event selector. The trail doesn’t log the event. 
         

        

        Type -> (string)

          

          The resource type in which you want to log data events. You can specify only the following value: ``AWS::S3::Object`` .

          

          

        Values -> (list)

          

          A list of ARN-like strings for the specified S3 objects.

           

          To log data events for all objects in an S3 bucket, specify the bucket and an empty object prefix such as ``arn:aws:s3:::bucket-1/`` . The trail logs data events for all objects in this S3 bucket.

           

          To log data events for specific objects, specify the S3 bucket and object prefix such as ``arn:aws:s3:::bucket-1/example-images`` . The trail logs data events for objects in this S3 bucket that match the prefix.

          

          (string)

            

            

          

        

      

    

  

