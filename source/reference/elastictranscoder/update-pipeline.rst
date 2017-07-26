[ :ref:`aws <cli:aws>` . :ref:`elastictranscoder <cli:aws elastictranscoder>` ]

.. _cli:aws elastictranscoder update-pipeline:


***************
update-pipeline
***************



===========
Description
===========



Use the ``update-pipeline`` operation to update settings for a pipeline.

 

.. warning::

   

  When you change pipeline settings, your changes take effect immediately. Jobs that you have already submitted and that Elastic Transcoder has not started to process are affected in addition to jobs that you submit after you change settings. 

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elastictranscoder-2012-09-25/UpdatePipeline>`_


========
Synopsis
========

::

    update-pipeline
  --id <value>
  [--name <value>]
  [--input-bucket <value>]
  [--role <value>]
  [--aws-kms-key-arn <value>]
  [--notifications <value>]
  [--content-config <value>]
  [--thumbnail-config <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the pipeline that you want to update.

  

``--name`` (string)


  The name of the pipeline. We recommend that the name be unique within the AWS account, but uniqueness is not enforced.

   

  Constraints: Maximum 40 characters

  

``--input-bucket`` (string)


  The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.

  

``--role`` (string)


  The IAM Amazon Resource name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.

  

``--aws-kms-key-arn`` (string)


  The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.

   

  If you use either ``S3`` or ``S3-AWS-KMS`` as your ``Encryption:Mode`` , you don't need to provide a key with your job because a default key, known as an AWS-KMS key, is created for you automatically. You need to provide an AWS-KMS key only if you want to use a non-default AWS-KMS key, or if you are using an ``Encryption:Mode`` of ``AES-PKCS7`` , ``AES-CTR`` , or ``AES-GCM`` .

  

``--notifications`` (structure)


  The topic ARN for the Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status.

   

  .. warning::

     

    To receive notifications, you must also subscribe to the new topic in the Amazon SNS console.

     

   

   
  * **Progressing** : The topic ARN for the Amazon Simple Notification Service (Amazon SNS) topic that you want to notify when Elastic Transcoder has started to process jobs that are added to this pipeline. This is the ARN that Amazon SNS returned when you created the topic. 
   
  * **Completed** : The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder has finished processing a job. This is the ARN that Amazon SNS returned when you created the topic. 
   
  * **Warning** : The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder encounters a warning condition. This is the ARN that Amazon SNS returned when you created the topic. 
   
  * **Error** : The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder encounters an error condition. This is the ARN that Amazon SNS returned when you created the topic. 
   

  



Shorthand Syntax::

    Progressing=string,Completed=string,Warning=string,Error=string




JSON Syntax::

  {
    "Progressing": "string",
    "Completed": "string",
    "Warning": "string",
    "Error": "string"
  }



``--content-config`` (structure)


  The optional ``ContentConfig`` object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists: which bucket to use, which users you want to have access to the files, the type of access you want users to have, and the storage class that you want to assign to the files.

   

  If you specify values for ``ContentConfig`` , you must also specify values for ``ThumbnailConfig`` .

   

  If you specify values for ``ContentConfig`` and ``ThumbnailConfig`` , omit the ``OutputBucket`` object.

   

   
  * **Bucket** : The Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. 
   
  * **Permissions** (Optional): The Permissions object specifies which users you want to have access to transcoded files and the type of access you want them to have. You can grant permissions to a maximum of 30 users and/or predefined Amazon S3 groups. 
   
  * **Grantee Type** : Specify the type of value that appears in the ``Grantee`` object: 

     
    * **Canonical** : The value in the ``Grantee`` object is either the canonical user ID for an AWS account or an origin access identity for an Amazon CloudFront distribution. For more information about canonical user IDs, see Access Control List (ACL) Overview in the Amazon Simple Storage Service Developer Guide. For more information about using CloudFront origin access identities to require that users use CloudFront URLs instead of Amazon S3 URLs, see Using an Origin Access Identity to Restrict Access to Your Amazon S3 Content. 

    .. warning::

       A canonical user ID is not the same as an AWS account number. 

     
     
    * **Email** : The value in the ``Grantee`` object is the registered email address of an AWS account. 
     
    * **Group** : The value in the ``Grantee`` object is one of the following predefined Amazon S3 groups: ``AllUsers`` , ``AuthenticatedUsers`` , or ``LogDelivery`` . 
     

   
   
  * **Grantee** : The AWS user or group that you want to have access to transcoded files and playlists. To identify the user or group, you can specify the canonical user ID for an AWS account, an origin access identity for a CloudFront distribution, the registered email address of an AWS account, or a predefined Amazon S3 group  
   
  * **Access** : The permission that you want to give to the AWS user that you specified in ``Grantee`` . Permissions are granted on the files that Elastic Transcoder adds to the bucket, including playlists and video files. Valid values include:  

     
    * ``READ`` : The grantee can read the objects and metadata for objects that Elastic Transcoder adds to the Amazon S3 bucket. 
     
    * ``READ_ACP`` : The grantee can read the object ACL for objects that Elastic Transcoder adds to the Amazon S3 bucket.  
     
    * ``WRITE_ACP`` : The grantee can write the ACL for the objects that Elastic Transcoder adds to the Amazon S3 bucket. 
     
    * ``FULL_CONTROL`` : The grantee has ``READ`` , ``READ_ACP`` , and ``WRITE_ACP`` permissions for the objects that Elastic Transcoder adds to the Amazon S3 bucket. 
     

   
   
  * **StorageClass** : The Amazon S3 storage class, ``Standard`` or ``ReducedRedundancy`` , that you want Elastic Transcoder to assign to the video files and playlists that it stores in your Amazon S3 bucket. 
   

  



JSON Syntax::

  {
    "Bucket": "string",
    "StorageClass": "string",
    "Permissions": [
      {
        "GranteeType": "string",
        "Grantee": "string",
        "Access": ["string", ...]
      }
      ...
    ]
  }



``--thumbnail-config`` (structure)


  The ``ThumbnailConfig`` object specifies several values, including the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files, which users you want to have access to the files, the type of access you want users to have, and the storage class that you want to assign to the files.

   

  If you specify values for ``ContentConfig`` , you must also specify values for ``ThumbnailConfig`` even if you don't want to create thumbnails.

   

  If you specify values for ``ContentConfig`` and ``ThumbnailConfig`` , omit the ``OutputBucket`` object.

   

   
  * **Bucket** : The Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. 
   
  * **Permissions** (Optional): The ``Permissions`` object specifies which users and/or predefined Amazon S3 groups you want to have access to thumbnail files, and the type of access you want them to have. You can grant permissions to a maximum of 30 users and/or predefined Amazon S3 groups. 
   
  * **GranteeType** : Specify the type of value that appears in the Grantee object: 

     
    * **Canonical** : The value in the ``Grantee`` object is either the canonical user ID for an AWS account or an origin access identity for an Amazon CloudFront distribution. 

    .. warning::

       A canonical user ID is not the same as an AWS account number. 

     
     
    * **Email** : The value in the ``Grantee`` object is the registered email address of an AWS account. 
     
    * **Group** : The value in the ``Grantee`` object is one of the following predefined Amazon S3 groups: ``AllUsers`` , ``AuthenticatedUsers`` , or ``LogDelivery`` . 
     

   
   
  * **Grantee** : The AWS user or group that you want to have access to thumbnail files. To identify the user or group, you can specify the canonical user ID for an AWS account, an origin access identity for a CloudFront distribution, the registered email address of an AWS account, or a predefined Amazon S3 group.  
   
  * **Access** : The permission that you want to give to the AWS user that you specified in ``Grantee`` . Permissions are granted on the thumbnail files that Elastic Transcoder adds to the bucket. Valid values include:  

     
    * ``READ`` : The grantee can read the thumbnails and metadata for objects that Elastic Transcoder adds to the Amazon S3 bucket. 
     
    * ``READ_ACP`` : The grantee can read the object ACL for thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
     
    * ``WRITE_ACP`` : The grantee can write the ACL for the thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
     
    * ``FULL_CONTROL`` : The grantee has ``READ`` , ``READ_ACP`` , and ``WRITE_ACP`` permissions for the thumbnails that Elastic Transcoder adds to the Amazon S3 bucket.  
     

   
   
  * **StorageClass** : The Amazon S3 storage class, ``Standard`` or ``ReducedRedundancy`` , that you want Elastic Transcoder to assign to the thumbnails that it stores in your Amazon S3 bucket. 
   

  



JSON Syntax::

  {
    "Bucket": "string",
    "StorageClass": "string",
    "Permissions": [
      {
        "GranteeType": "string",
        "Grantee": "string",
        "Access": ["string", ...]
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Pipeline -> (structure)

  

  The pipeline updated by this ``UpdatePipelineResponse`` call.

  

  Id -> (string)

    

    The identifier for the pipeline. You use this value to identify the pipeline in which you want to perform a variety of operations, such as creating a job or a preset.

    

    

  Arn -> (string)

    

    The Amazon Resource name (ARN) for the pipeline.

    

    

  Name -> (string)

    

    The name of the pipeline. We recommend that the name be unique within the AWS account, but uniqueness is not enforced.

     

    Constraints: Maximum 40 characters

    

    

  Status -> (string)

    

    The current status of the pipeline:

     

     
    * ``Active`` : The pipeline is processing jobs. 
     
    * ``Paused`` : The pipeline is not currently processing jobs. 
     

    

    

  InputBucket -> (string)

    

    The Amazon S3 bucket from which Elastic Transcoder gets media files for transcoding and the graphics files, if any, that you want to use for watermarks.

    

    

  OutputBucket -> (string)

    

    The Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files, thumbnails, and playlists. Either you specify this value, or you specify both ``ContentConfig`` and ``ThumbnailConfig`` .

    

    

  Role -> (string)

    

    The IAM Amazon Resource name (ARN) for the role that Elastic Transcoder uses to transcode jobs for this pipeline.

    

    

  AwsKmsKeyArn -> (string)

    

    The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.

     

    If you use either ``S3`` or ``S3-AWS-KMS`` as your ``Encryption:Mode`` , you don't need to provide a key with your job because a default key, known as an AWS-KMS key, is created for you automatically. You need to provide an AWS-KMS key only if you want to use a non-default AWS-KMS key, or if you are using an ``Encryption:Mode`` of ``AES-PKCS7`` , ``AES-CTR`` , or ``AES-GCM`` .

    

    

  Notifications -> (structure)

    

    The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status.

     

    .. warning::

       

      To receive notifications, you must also subscribe to the new topic in the Amazon SNS console.

       

     

     
    * **Progressing** (optional): The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify when Elastic Transcoder has started to process the job. 
     
    * **Completed** (optional): The Amazon SNS topic that you want to notify when Elastic Transcoder has finished processing the job. 
     
    * **Warning** (optional): The Amazon SNS topic that you want to notify when Elastic Transcoder encounters a warning condition. 
     
    * **Error** (optional): The Amazon SNS topic that you want to notify when Elastic Transcoder encounters an error condition. 
     

    

    Progressing -> (string)

      

      The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify when Elastic Transcoder has started to process the job.

      

      

    Completed -> (string)

      

      The Amazon SNS topic that you want to notify when Elastic Transcoder has finished processing the job.

      

      

    Warning -> (string)

      

      The Amazon SNS topic that you want to notify when Elastic Transcoder encounters a warning condition.

      

      

    Error -> (string)

      

      The Amazon SNS topic that you want to notify when Elastic Transcoder encounters an error condition.

      

      

    

  ContentConfig -> (structure)

    

    Information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. Either you specify both ``ContentConfig`` and ``ThumbnailConfig`` , or you specify ``OutputBucket`` .

     

     
    * **Bucket** : The Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. 
     
    * **Permissions** : A list of the users and/or predefined Amazon S3 groups you want to have access to transcoded files and playlists, and the type of access that you want them to have.  

       
      * GranteeType: The type of value that appears in the ``Grantee`` object:  

         
        * ``Canonical`` : Either the canonical user ID for an AWS account or an origin access identity for an Amazon CloudFront distribution. 
         
        * ``Email`` : The registered email address of an AWS account. 
         
        * ``Group`` : One of the following predefined Amazon S3 groups: ``AllUsers`` , ``AuthenticatedUsers`` , or ``LogDelivery`` . 
         

       
       
      * ``Grantee`` : The AWS user or group that you want to have access to transcoded files and playlists. 
       
      * ``Access`` : The permission that you want to give to the AWS user that is listed in ``Grantee`` . Valid values include: 

         
        * ``READ`` : The grantee can read the objects and metadata for objects that Elastic Transcoder adds to the Amazon S3 bucket. 
         
        * ``READ_ACP`` : The grantee can read the object ACL for objects that Elastic Transcoder adds to the Amazon S3 bucket. 
         
        * ``WRITE_ACP`` : The grantee can write the ACL for the objects that Elastic Transcoder adds to the Amazon S3 bucket. 
         
        * ``FULL_CONTROL`` : The grantee has ``READ`` , ``READ_ACP`` , and ``WRITE_ACP`` permissions for the objects that Elastic Transcoder adds to the Amazon S3 bucket. 
         

       
       

     
     
    * **StorageClass** : The Amazon S3 storage class, Standard or ReducedRedundancy, that you want Elastic Transcoder to assign to the video files and playlists that it stores in your Amazon S3 bucket.  
     

    

    Bucket -> (string)

      

      The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files. Specify this value when all of the following are true:

       

       
      * You want to save transcoded files, thumbnails (if any), and playlists (if any) together in one bucket. 
       
      * You do not want to specify the users or groups who have access to the transcoded files, thumbnails, and playlists. 
       
      * You do not want to specify the permissions that Elastic Transcoder grants to the files. 
       
      * You want to associate the transcoded files and thumbnails with the Amazon S3 Standard storage class. 
       

       

      If you want to save transcoded files and playlists in one bucket and thumbnails in another bucket, specify which users can access the transcoded files or the permissions the users have, or change the Amazon S3 storage class, omit OutputBucket and specify values for ``ContentConfig`` and ``ThumbnailConfig`` instead. 

      

      

    StorageClass -> (string)

      

      The Amazon S3 storage class, ``Standard`` or ``ReducedRedundancy`` , that you want Elastic Transcoder to assign to the video files and playlists that it stores in your Amazon S3 bucket. 

      

      

    Permissions -> (list)

      

      Optional. The ``Permissions`` object specifies which users and/or predefined Amazon S3 groups you want to have access to transcoded files and playlists, and the type of access you want them to have. You can grant permissions to a maximum of 30 users and/or predefined Amazon S3 groups.

       

      If you include ``Permissions`` , Elastic Transcoder grants only the permissions that you specify. It does not grant full permissions to the owner of the role specified by ``role`` . If you want that user to have full control, you must explicitly grant full control to the user.

       

      If you omit ``Permissions`` , Elastic Transcoder grants full control over the transcoded files and playlists to the owner of the role specified by ``role`` , and grants no other permissions to any other user or group.

      

      (structure)

        

        The ``Permission`` structure.

        

        GranteeType -> (string)

          

          The type of value that appears in the Grantee object:

           

           
          * ``Canonical`` : Either the canonical user ID for an AWS account or an origin access identity for an Amazon CloudFront distribution. 

          .. warning::

             A canonical user ID is not the same as an AWS account number. 

           
           
          * ``Email`` : The registered email address of an AWS account. 
           
          * ``Group`` : One of the following predefined Amazon S3 groups: ``AllUsers`` , ``AuthenticatedUsers`` , or ``LogDelivery`` . 
           

          

          

        Grantee -> (string)

          

          The AWS user or group that you want to have access to transcoded files and playlists. To identify the user or group, you can specify the canonical user ID for an AWS account, an origin access identity for a CloudFront distribution, the registered email address of an AWS account, or a predefined Amazon S3 group.

          

          

        Access -> (list)

          

          The permission that you want to give to the AWS user that is listed in Grantee. Valid values include: 

           

           
          * ``READ`` : The grantee can read the thumbnails and metadata for thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
           
          * ``READ_ACP`` : The grantee can read the object ACL for thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
           
          * ``WRITE_ACP`` : The grantee can write the ACL for the thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
           
          * ``FULL_CONTROL`` : The grantee has READ, READ_ACP, and WRITE_ACP permissions for the thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
           

          

          (string)

            

            

          

        

      

    

  ThumbnailConfig -> (structure)

    

    Information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. Either you specify both ``ContentConfig`` and ``ThumbnailConfig`` , or you specify ``OutputBucket`` .

     

     
    * ``Bucket`` : The Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files.  
     
    * ``Permissions`` : A list of the users and/or predefined Amazon S3 groups you want to have access to thumbnail files, and the type of access that you want them to have.  

       
      * GranteeType: The type of value that appears in the Grantee object: 

         
        * ``Canonical`` : Either the canonical user ID for an AWS account or an origin access identity for an Amazon CloudFront distribution. 

        .. warning::

           A canonical user ID is not the same as an AWS account number. 

         
         
        * ``Email`` : The registered email address of an AWS account. 
         
        * ``Group`` : One of the following predefined Amazon S3 groups: ``AllUsers`` , ``AuthenticatedUsers`` , or ``LogDelivery`` . 
         

       
       
      * ``Grantee`` : The AWS user or group that you want to have access to thumbnail files. 
       
      * Access: The permission that you want to give to the AWS user that is listed in Grantee. Valid values include:  

         
        * ``READ`` : The grantee can read the thumbnails and metadata for thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
         
        * ``READ_ACP`` : The grantee can read the object ACL for thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
         
        * ``WRITE_ACP`` : The grantee can write the ACL for the thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
         
        * ``FULL_CONTROL`` : The grantee has READ, READ_ACP, and WRITE_ACP permissions for the thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
         

       
       

     
     
    * ``StorageClass`` : The Amazon S3 storage class, ``Standard`` or ``ReducedRedundancy`` , that you want Elastic Transcoder to assign to the thumbnails that it stores in your Amazon S3 bucket. 
     

    

    Bucket -> (string)

      

      The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files. Specify this value when all of the following are true:

       

       
      * You want to save transcoded files, thumbnails (if any), and playlists (if any) together in one bucket. 
       
      * You do not want to specify the users or groups who have access to the transcoded files, thumbnails, and playlists. 
       
      * You do not want to specify the permissions that Elastic Transcoder grants to the files. 
       
      * You want to associate the transcoded files and thumbnails with the Amazon S3 Standard storage class. 
       

       

      If you want to save transcoded files and playlists in one bucket and thumbnails in another bucket, specify which users can access the transcoded files or the permissions the users have, or change the Amazon S3 storage class, omit OutputBucket and specify values for ``ContentConfig`` and ``ThumbnailConfig`` instead. 

      

      

    StorageClass -> (string)

      

      The Amazon S3 storage class, ``Standard`` or ``ReducedRedundancy`` , that you want Elastic Transcoder to assign to the video files and playlists that it stores in your Amazon S3 bucket. 

      

      

    Permissions -> (list)

      

      Optional. The ``Permissions`` object specifies which users and/or predefined Amazon S3 groups you want to have access to transcoded files and playlists, and the type of access you want them to have. You can grant permissions to a maximum of 30 users and/or predefined Amazon S3 groups.

       

      If you include ``Permissions`` , Elastic Transcoder grants only the permissions that you specify. It does not grant full permissions to the owner of the role specified by ``role`` . If you want that user to have full control, you must explicitly grant full control to the user.

       

      If you omit ``Permissions`` , Elastic Transcoder grants full control over the transcoded files and playlists to the owner of the role specified by ``role`` , and grants no other permissions to any other user or group.

      

      (structure)

        

        The ``Permission`` structure.

        

        GranteeType -> (string)

          

          The type of value that appears in the Grantee object:

           

           
          * ``Canonical`` : Either the canonical user ID for an AWS account or an origin access identity for an Amazon CloudFront distribution. 

          .. warning::

             A canonical user ID is not the same as an AWS account number. 

           
           
          * ``Email`` : The registered email address of an AWS account. 
           
          * ``Group`` : One of the following predefined Amazon S3 groups: ``AllUsers`` , ``AuthenticatedUsers`` , or ``LogDelivery`` . 
           

          

          

        Grantee -> (string)

          

          The AWS user or group that you want to have access to transcoded files and playlists. To identify the user or group, you can specify the canonical user ID for an AWS account, an origin access identity for a CloudFront distribution, the registered email address of an AWS account, or a predefined Amazon S3 group.

          

          

        Access -> (list)

          

          The permission that you want to give to the AWS user that is listed in Grantee. Valid values include: 

           

           
          * ``READ`` : The grantee can read the thumbnails and metadata for thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
           
          * ``READ_ACP`` : The grantee can read the object ACL for thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
           
          * ``WRITE_ACP`` : The grantee can write the ACL for the thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
           
          * ``FULL_CONTROL`` : The grantee has READ, READ_ACP, and WRITE_ACP permissions for the thumbnails that Elastic Transcoder adds to the Amazon S3 bucket. 
           

          

          (string)

            

            

          

        

      

    

  

Warnings -> (list)

  

  Elastic Transcoder returns a warning if the resources used by your pipeline are not in the same region as the pipeline.

   

  Using resources in the same region, such as your Amazon S3 buckets, Amazon SNS notification topics, and AWS KMS key, reduces processing time and prevents cross-regional charges.

  

  (structure)

    

    Elastic Transcoder returns a warning if the resources used by your pipeline are not in the same region as the pipeline.

     

    Using resources in the same region, such as your Amazon S3 buckets, Amazon SNS notification topics, and AWS KMS key, reduces processing time and prevents cross-regional charges.

    

    Code -> (string)

      

      The code of the cross-regional warning.

      

      

    Message -> (string)

      

      The message explaining what resources are in a different region from the pipeline.

       

      .. note::

         

        AWS KMS keys must be in the same region as the pipeline.

         

      

      

    

  

