[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball describe-cluster:


****************
describe-cluster
****************



===========
Description
===========



Returns information about a specific cluster including shipping information, cluster status, and other important metadata.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/DescribeCluster>`_


========
Synopsis
========

::

    describe-cluster
  --cluster-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The automatically generated ID for a cluster.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ClusterMetadata -> (structure)

  

  Information about a specific cluster, including shipping information, cluster status, and other important metadata.

  

  ClusterId -> (string)

    

    The automatically generated ID for a cluster.

    

    

  Description -> (string)

    

    The optional description of the cluster.

    

    

  KmsKeyARN -> (string)

    

    The ``KmsKeyARN`` Amazon Resource Name (ARN) associated with this cluster. This ARN was created using the `CreateKey <http://docs.aws.amazon.com/kms/latest/APIReference/API_CreateKey.html>`_ API action in AWS Key Management Service (AWS KMS).

    

    

  RoleARN -> (string)

    

    The role ARN associated with this cluster. This ARN was created using the `CreateRole <http://docs.aws.amazon.com/IAM/latest/APIReference/API_CreateRole.html>`_ API action in AWS Identity and Access Management (IAM).

    

    

  ClusterState -> (string)

    

    The current status of the cluster.

    

    

  JobType -> (string)

    

    The type of job for this cluster. Currently, the only job type supported for clusters is ``LOCAL_USE`` .

    

    

  SnowballType -> (string)

    

    The type of AWS Snowball appliance to use for this cluster. Currently, the only supported appliance type for cluster jobs is ``EDGE`` .

    

    

  CreationDate -> (timestamp)

    

    The creation date for this cluster.

    

    

  Resources -> (structure)

    

    The arrays of  JobResource objects that can include updated  S3Resource objects or  LambdaResource objects.

    

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

              

              

            

          

        

      

    

  AddressId -> (string)

    

    The automatically generated ID for a specific address.

    

    

  ShippingOption -> (string)

    

    The shipping speed for each node in this cluster. This speed doesn't dictate how soon you'll get each Snowball Edge appliance, rather it represents how quickly each appliance moves to its destination while in transit. Regional shipping speeds are as follows:

     

     
    * In Australia, you have access to express shipping. Typically, appliances shipped express are delivered in about a day. 
     
    * In the European Union (EU), you have access to express shipping. Typically, Snowball Edges shipped express are delivered in about a day. In addition, most countries in the EU have access to standard shipping, which typically takes less than a week, one way. 
     
    * In India, Snowball Edges are delivered in one to seven days. 
     
    * In the US, you have access to one-day shipping and two-day shipping. 
     

    

    

  Notification -> (structure)

    

    The Amazon Simple Notification Service (Amazon SNS) notification settings for this cluster.

    

    SnsTopicARN -> (string)

      

      The new SNS ``TopicArn`` that you want to associate with this job. You can create Amazon Resource Names (ARNs) for topics by using the `CreateTopic <http://docs.aws.amazon.com/sns/latest/api/API_CreateTopic.html>`_ Amazon SNS API action.

       

      You can subscribe email addresses to an Amazon SNS topic through the AWS Management Console, or by using the `Subscribe <http://docs.aws.amazon.com/sns/latest/api/API_Subscribe.html>`_ AWS Simple Notification Service (SNS) API action.

      

      

    JobStatesToNotify -> (list)

      

      The list of job states that will trigger a notification for this job.

      

      (string)

        

        

      

    NotifyAll -> (boolean)

      

      Any change in job state will trigger a notification for this job.

      

      

    

  ForwardingAddressId -> (string)

    

    The ID of the address that you want a cluster shipped to, after it will be shipped to its primary address. This field is not supported in most regions.

    

    

  

