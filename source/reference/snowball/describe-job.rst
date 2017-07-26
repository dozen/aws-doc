[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball describe-job:


************
describe-job
************



===========
Description
===========



Returns information about a specific job including shipping information, job status, and other important metadata. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/DescribeJob>`_


========
Synopsis
========

::

    describe-job
  --job-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)


  The automatically generated ID for a job, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

JobMetadata -> (structure)

  

  Information about a specific job, including shipping information, job status, and other important metadata.

  

  JobId -> (string)

    

    The automatically generated ID for a job, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

    

    

  JobState -> (string)

    

    The current status of the jobs.

    

    

  JobType -> (string)

    

    The type of job.

    

    

  SnowballType -> (string)

    

    The type of appliance used with this job.

    

    

  CreationDate -> (timestamp)

    

    The creation date for this job.

    

    

  Resources -> (structure)

    

    An array of ``S3Resource`` objects. Each ``S3Resource`` object represents an Amazon S3 bucket that your transferred data will be exported from or imported into.

    

    S3Resources -> (list)

      

      An array of ``S3Resource`` objects.

      

      (structure)

        

        Each ``S3Resource`` object represents an Amazon S3 bucket that your transferred data will be exported from or imported into. For export jobs, this object can have an optional ``KeyRange`` value. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

        

        BucketArn -> (string)

          

          The Amazon Resource Name (ARN) of an Amazon S3 bucket.

          

          

        KeyRange -> (structure)

          

          For export jobs, you can provide an optional ``KeyRange`` within a specific Amazon S3 bucket. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

          

          BeginMarker -> (string)

            

            The key that starts an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

            

            

          EndMarker -> (string)

            

            The key that ends an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

            

            

          

        

      

    LambdaResources -> (list)

      

      The Python-language Lambda functions for this job.

      

      (structure)

        

        Identifies 

        

        LambdaArn -> (string)

          

          An Amazon Resource Name (ARN) that represents an AWS Lambda function to be triggered by PUT object actions on the associated local Amazon S3 resource.

          

          

        EventTriggers -> (list)

          

          The array of ARNs for  S3Resource objects to trigger the  LambdaResource objects associated with this job.

          

          (structure)

            

            The container for the  EventTriggerDefinition$EventResourceARN .

            

            EventResourceARN -> (string)

              

              The Amazon Resource Name (ARN) for any local Amazon S3 resource that is an AWS Lambda function's event trigger associated with this job.

              

              

            

          

        

      

    

  Description -> (string)

    

    The description of the job, provided at job creation.

    

    

  KmsKeyARN -> (string)

    

    The Amazon Resource Name (ARN) for the AWS Key Management Service (AWS KMS) key associated with this job. This ARN was created using the `CreateKey <http://docs.aws.amazon.com/kms/latest/APIReference/API_CreateKey.html>`_ API action in AWS KMS.

    

    

  RoleARN -> (string)

    

    The role ARN associated with this job. This ARN was created using the `CreateRole <http://docs.aws.amazon.com/IAM/latest/APIReference/API_CreateRole.html>`_ API action in AWS Identity and Access Management (IAM).

    

    

  AddressId -> (string)

    

    The ID for the address that you want the Snowball shipped to.

    

    

  ShippingDetails -> (structure)

    

    A job's shipping information, including inbound and outbound tracking numbers and shipping speed options.

    

    ShippingOption -> (string)

      

      The shipping speed for a particular job. This speed doesn't dictate how soon you'll get the Snowball from the job's creation date. This speed represents how quickly it moves to its destination while in transit. Regional shipping speeds are as follows:

       

       
      * In Australia, you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. 
       
      * In the European Union (EU), you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. In addition, most countries in the EU have access to standard shipping, which typically takes less than a week, one way. 
       
      * In India, Snowballs are delivered in one to seven days. 
       
      * In the United States of America (US), you have access to one-day shipping and two-day shipping. 
       

      

      

    InboundShipment -> (structure)

      

      The ``Status`` and ``TrackingNumber`` values for a Snowball being delivered to the address that you specified for a particular job.

      

      Status -> (string)

        

        Status information for a shipment.

        

        

      TrackingNumber -> (string)

        

        The tracking number for this job. Using this tracking number with your region's carrier's website, you can track a Snowball as the carrier transports it.

         

        For India, the carrier is Amazon Logistics. For all other regions, UPS is the carrier.

        

        

      

    OutboundShipment -> (structure)

      

      The ``Status`` and ``TrackingNumber`` values for a Snowball being returned to AWS for a particular job.

      

      Status -> (string)

        

        Status information for a shipment.

        

        

      TrackingNumber -> (string)

        

        The tracking number for this job. Using this tracking number with your region's carrier's website, you can track a Snowball as the carrier transports it.

         

        For India, the carrier is Amazon Logistics. For all other regions, UPS is the carrier.

        

        

      

    

  SnowballCapacityPreference -> (string)

    

    The Snowball capacity preference for this job, specified at job creation. In US regions, you can choose between 50 TB and 80 TB Snowballs. All other regions use 80 TB capacity Snowballs.

    

    

  Notification -> (structure)

    

    The Amazon Simple Notification Service (Amazon SNS) notification settings associated with a specific job. The ``Notification`` object is returned as a part of the response syntax of the ``describe-job`` action in the ``JobMetadata`` data type.

    

    SnsTopicARN -> (string)

      

      The new SNS ``TopicArn`` that you want to associate with this job. You can create Amazon Resource Names (ARNs) for topics by using the `CreateTopic <http://docs.aws.amazon.com/sns/latest/api/API_CreateTopic.html>`_ Amazon SNS API action.

       

      You can subscribe email addresses to an Amazon SNS topic through the AWS Management Console, or by using the `Subscribe <http://docs.aws.amazon.com/sns/latest/api/API_Subscribe.html>`_ AWS Simple Notification Service (SNS) API action.

      

      

    JobStatesToNotify -> (list)

      

      The list of job states that will trigger a notification for this job.

      

      (string)

        

        

      

    NotifyAll -> (boolean)

      

      Any change in job state will trigger a notification for this job.

      

      

    

  DataTransferProgress -> (structure)

    

    A value that defines the real-time status of a Snowball's data transfer while the appliance is at AWS. This data is only available while a job has a ``JobState`` value of ``InProgress`` , for both import and export jobs.

    

    BytesTransferred -> (long)

      

      The number of bytes transferred between a Snowball and Amazon S3.

      

      

    ObjectsTransferred -> (long)

      

      The number of objects transferred between a Snowball and Amazon S3.

      

      

    TotalBytes -> (long)

      

      The total bytes of data for a transfer between a Snowball and Amazon S3. This value is set to 0 (zero) until all the keys that will be transferred have been listed.

      

      

    TotalObjects -> (long)

      

      The total number of objects for a transfer between a Snowball and Amazon S3. This value is set to 0 (zero) until all the keys that will be transferred have been listed.

      

      

    

  JobLogInfo -> (structure)

    

    Links to Amazon S3 presigned URLs for the job report and logs. For import jobs, the PDF job report becomes available at the end of the import process. For export jobs, your job report typically becomes available while the Snowball for your job part is being delivered to you.

    

    JobCompletionReportURI -> (string)

      

      A link to an Amazon S3 presigned URL where the job completion report is located.

      

      

    JobSuccessLogURI -> (string)

      

      A link to an Amazon S3 presigned URL where the job success log is located.

      

      

    JobFailureLogURI -> (string)

      

      A link to an Amazon S3 presigned URL where the job failure log is located.

      

      

    

  ClusterId -> (string)

    

    The 39-character ID for the cluster, for example ``CID123e4567-e89b-12d3-a456-426655440000`` .

    

    

  ForwardingAddressId -> (string)

    

    The ID of the address that you want a job shipped to, after it will be shipped to its primary address. This field is not supported in most regions.

    

    

  

SubJobMetadata -> (list)

  

  Information about a specific job part (in the case of an export job), including shipping information, job status, and other important metadata.

  

  (structure)

    

    Contains information about a specific job including shipping information, job status, and other important metadata. This information is returned as a part of the response syntax of the ``describe-job`` action.

    

    JobId -> (string)

      

      The automatically generated ID for a job, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

      

      

    JobState -> (string)

      

      The current status of the jobs.

      

      

    JobType -> (string)

      

      The type of job.

      

      

    SnowballType -> (string)

      

      The type of appliance used with this job.

      

      

    CreationDate -> (timestamp)

      

      The creation date for this job.

      

      

    Resources -> (structure)

      

      An array of ``S3Resource`` objects. Each ``S3Resource`` object represents an Amazon S3 bucket that your transferred data will be exported from or imported into.

      

      S3Resources -> (list)

        

        An array of ``S3Resource`` objects.

        

        (structure)

          

          Each ``S3Resource`` object represents an Amazon S3 bucket that your transferred data will be exported from or imported into. For export jobs, this object can have an optional ``KeyRange`` value. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

          

          BucketArn -> (string)

            

            The Amazon Resource Name (ARN) of an Amazon S3 bucket.

            

            

          KeyRange -> (structure)

            

            For export jobs, you can provide an optional ``KeyRange`` within a specific Amazon S3 bucket. The length of the range is defined at job creation, and has either an inclusive ``BeginMarker`` , an inclusive ``EndMarker`` , or both. Ranges are UTF-8 binary sorted.

            

            BeginMarker -> (string)

              

              The key that starts an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

              

              

            EndMarker -> (string)

              

              The key that ends an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.

              

              

            

          

        

      LambdaResources -> (list)

        

        The Python-language Lambda functions for this job.

        

        (structure)

          

          Identifies 

          

          LambdaArn -> (string)

            

            An Amazon Resource Name (ARN) that represents an AWS Lambda function to be triggered by PUT object actions on the associated local Amazon S3 resource.

            

            

          EventTriggers -> (list)

            

            The array of ARNs for  S3Resource objects to trigger the  LambdaResource objects associated with this job.

            

            (structure)

              

              The container for the  EventTriggerDefinition$EventResourceARN .

              

              EventResourceARN -> (string)

                

                The Amazon Resource Name (ARN) for any local Amazon S3 resource that is an AWS Lambda function's event trigger associated with this job.

                

                

              

            

          

        

      

    Description -> (string)

      

      The description of the job, provided at job creation.

      

      

    KmsKeyARN -> (string)

      

      The Amazon Resource Name (ARN) for the AWS Key Management Service (AWS KMS) key associated with this job. This ARN was created using the `CreateKey <http://docs.aws.amazon.com/kms/latest/APIReference/API_CreateKey.html>`_ API action in AWS KMS.

      

      

    RoleARN -> (string)

      

      The role ARN associated with this job. This ARN was created using the `CreateRole <http://docs.aws.amazon.com/IAM/latest/APIReference/API_CreateRole.html>`_ API action in AWS Identity and Access Management (IAM).

      

      

    AddressId -> (string)

      

      The ID for the address that you want the Snowball shipped to.

      

      

    ShippingDetails -> (structure)

      

      A job's shipping information, including inbound and outbound tracking numbers and shipping speed options.

      

      ShippingOption -> (string)

        

        The shipping speed for a particular job. This speed doesn't dictate how soon you'll get the Snowball from the job's creation date. This speed represents how quickly it moves to its destination while in transit. Regional shipping speeds are as follows:

         

         
        * In Australia, you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. 
         
        * In the European Union (EU), you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. In addition, most countries in the EU have access to standard shipping, which typically takes less than a week, one way. 
         
        * In India, Snowballs are delivered in one to seven days. 
         
        * In the United States of America (US), you have access to one-day shipping and two-day shipping. 
         

        

        

      InboundShipment -> (structure)

        

        The ``Status`` and ``TrackingNumber`` values for a Snowball being delivered to the address that you specified for a particular job.

        

        Status -> (string)

          

          Status information for a shipment.

          

          

        TrackingNumber -> (string)

          

          The tracking number for this job. Using this tracking number with your region's carrier's website, you can track a Snowball as the carrier transports it.

           

          For India, the carrier is Amazon Logistics. For all other regions, UPS is the carrier.

          

          

        

      OutboundShipment -> (structure)

        

        The ``Status`` and ``TrackingNumber`` values for a Snowball being returned to AWS for a particular job.

        

        Status -> (string)

          

          Status information for a shipment.

          

          

        TrackingNumber -> (string)

          

          The tracking number for this job. Using this tracking number with your region's carrier's website, you can track a Snowball as the carrier transports it.

           

          For India, the carrier is Amazon Logistics. For all other regions, UPS is the carrier.

          

          

        

      

    SnowballCapacityPreference -> (string)

      

      The Snowball capacity preference for this job, specified at job creation. In US regions, you can choose between 50 TB and 80 TB Snowballs. All other regions use 80 TB capacity Snowballs.

      

      

    Notification -> (structure)

      

      The Amazon Simple Notification Service (Amazon SNS) notification settings associated with a specific job. The ``Notification`` object is returned as a part of the response syntax of the ``describe-job`` action in the ``JobMetadata`` data type.

      

      SnsTopicARN -> (string)

        

        The new SNS ``TopicArn`` that you want to associate with this job. You can create Amazon Resource Names (ARNs) for topics by using the `CreateTopic <http://docs.aws.amazon.com/sns/latest/api/API_CreateTopic.html>`_ Amazon SNS API action.

         

        You can subscribe email addresses to an Amazon SNS topic through the AWS Management Console, or by using the `Subscribe <http://docs.aws.amazon.com/sns/latest/api/API_Subscribe.html>`_ AWS Simple Notification Service (SNS) API action.

        

        

      JobStatesToNotify -> (list)

        

        The list of job states that will trigger a notification for this job.

        

        (string)

          

          

        

      NotifyAll -> (boolean)

        

        Any change in job state will trigger a notification for this job.

        

        

      

    DataTransferProgress -> (structure)

      

      A value that defines the real-time status of a Snowball's data transfer while the appliance is at AWS. This data is only available while a job has a ``JobState`` value of ``InProgress`` , for both import and export jobs.

      

      BytesTransferred -> (long)

        

        The number of bytes transferred between a Snowball and Amazon S3.

        

        

      ObjectsTransferred -> (long)

        

        The number of objects transferred between a Snowball and Amazon S3.

        

        

      TotalBytes -> (long)

        

        The total bytes of data for a transfer between a Snowball and Amazon S3. This value is set to 0 (zero) until all the keys that will be transferred have been listed.

        

        

      TotalObjects -> (long)

        

        The total number of objects for a transfer between a Snowball and Amazon S3. This value is set to 0 (zero) until all the keys that will be transferred have been listed.

        

        

      

    JobLogInfo -> (structure)

      

      Links to Amazon S3 presigned URLs for the job report and logs. For import jobs, the PDF job report becomes available at the end of the import process. For export jobs, your job report typically becomes available while the Snowball for your job part is being delivered to you.

      

      JobCompletionReportURI -> (string)

        

        A link to an Amazon S3 presigned URL where the job completion report is located.

        

        

      JobSuccessLogURI -> (string)

        

        A link to an Amazon S3 presigned URL where the job success log is located.

        

        

      JobFailureLogURI -> (string)

        

        A link to an Amazon S3 presigned URL where the job failure log is located.

        

        

      

    ClusterId -> (string)

      

      The 39-character ID for the cluster, for example ``CID123e4567-e89b-12d3-a456-426655440000`` .

      

      

    ForwardingAddressId -> (string)

      

      The ID of the address that you want a job shipped to, after it will be shipped to its primary address. This field is not supported in most regions.

      

      

    

  

