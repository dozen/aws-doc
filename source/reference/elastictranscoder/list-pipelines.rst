[ :ref:`aws <cli:aws>` . :ref:`elastictranscoder <cli:aws elastictranscoder>` ]

.. _cli:aws elastictranscoder list-pipelines:


**************
list-pipelines
**************



===========
Description
===========



The list-pipelines operation gets a list of the pipelines associated with the current AWS account.



``list-pipelines`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Pipelines``


========
Synopsis
========

::

    list-pipelines
  [--ascending <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ascending`` (string)


  To list pipelines in chronological order by the date and time that they were created, enter ``true`` . To list pipelines in reverse chronological order, enter ``false`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Pipelines -> (list)

  

  An array of ``Pipeline`` objects.

  

  (structure)

    

    The pipeline (queue) that is used to manage jobs.

    

    Id -> (string)

      

      The identifier for the pipeline. You use this value to identify the pipeline in which you want to perform a variety of operations, such as creating a job or a preset. 

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) for the pipeline.

      

      

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

      

      The IAM Amazon Resource Name (ARN) for the role that Elastic Transcoder uses to transcode jobs for this pipeline.

      

      

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

         

        If you include ``Permissions`` , Elastic Transcoder grants only the permissions that you specify. It does not grant full permissions to the owner of the role specified by ``Role`` . If you want that user to have full control, you must explicitly grant full control to the user.

         

        If you omit ``Permissions`` , Elastic Transcoder grants full control over the transcoded files and playlists to the owner of the role specified by ``Role`` , and grants no other permissions to any other user or group.

        

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

         

        If you include ``Permissions`` , Elastic Transcoder grants only the permissions that you specify. It does not grant full permissions to the owner of the role specified by ``Role`` . If you want that user to have full control, you must explicitly grant full control to the user.

         

        If you omit ``Permissions`` , Elastic Transcoder grants full control over the transcoded files and playlists to the owner of the role specified by ``Role`` , and grants no other permissions to any other user or group.

        

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

              

              

            

          

        

      

    

  

NextPageToken -> (string)

  

  A value that you use to access the second and subsequent pages of results, if any. When the pipelines fit on one page or when you've reached the last page of results, the value of ``NextPageToken`` is ``null`` .

  

  

