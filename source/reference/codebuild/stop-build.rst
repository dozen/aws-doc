[ :ref:`aws <cli:aws>` . :ref:`codebuild <cli:aws codebuild>` ]

.. _cli:aws codebuild stop-build:


**********
stop-build
**********



===========
Description
===========



Attempts to stop running a build.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codebuild-2016-10-06/StopBuild>`_


========
Synopsis
========

::

    stop-build
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the build.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

build -> (structure)

  

  Information about the build.

  

  id -> (string)

    

    The unique ID for the build.

    

    

  arn -> (string)

    

    The Amazon Resource Name (ARN) of the build.

    

    

  startTime -> (timestamp)

    

    When the build process started, expressed in Unix time format.

    

    

  endTime -> (timestamp)

    

    When the build process ended, expressed in Unix time format.

    

    

  currentPhase -> (string)

    

    The current build phase.

    

    

  buildStatus -> (string)

    

    The current status of the build. Valid values include:

     

     
    * ``FAILED`` : The build failed. 
     
    * ``FAULT`` : The build faulted. 
     
    * ``IN_PROGRESS`` : The build is still in progress. 
     
    * ``STOPPED`` : The build stopped. 
     
    * ``SUCCEEDED`` : The build succeeded. 
     
    * ``TIMED_OUT`` : The build timed out. 
     

    

    

  sourceVersion -> (string)

    

    Any version identifier for the version of the source code to be built.

    

    

  projectName -> (string)

    

    The name of the build project.

    

    

  phases -> (list)

    

    Information about all previous build phases that are completed and information about any current build phase that is not yet complete.

    

    (structure)

      

      Information about a stage for a build.

      

      phaseType -> (string)

        

        The name of the build phase. Valid values include:

         

         
        * ``BUILD`` : Core build activities typically occur in this build phase. 
         
        * ``COMPLETED`` : The build has been completed. 
         
        * ``DOWNLOAD_SOURCE`` : Source code is being downloaded in this build phase. 
         
        * ``FINALIZING`` : The build process is completing in this build phase. 
         
        * ``INSTALL`` : Installation activities typically occur in this build phase. 
         
        * ``POST_BUILD`` : Post-build activities typically occur in this build phase. 
         
        * ``PRE_BUILD`` : Pre-build activities typically occur in this build phase. 
         
        * ``PROVISIONING`` : The build environment is being set up. 
         
        * ``SUBMITTED`` : The build has been submitted. 
         
        * ``UPLOAD_ARTIFACTS`` : Build output artifacts are being uploaded to the output location. 
         

        

        

      phaseStatus -> (string)

        

        The current status of the build phase. Valid values include:

         

         
        * ``FAILED`` : The build phase failed. 
         
        * ``FAULT`` : The build phase faulted. 
         
        * ``IN_PROGRESS`` : The build phase is still in progress. 
         
        * ``STOPPED`` : The build phase stopped. 
         
        * ``SUCCEEDED`` : The build phase succeeded. 
         
        * ``TIMED_OUT`` : The build phase timed out. 
         

        

        

      startTime -> (timestamp)

        

        When the build phase started, expressed in Unix time format.

        

        

      endTime -> (timestamp)

        

        When the build phase ended, expressed in Unix time format.

        

        

      durationInSeconds -> (long)

        

        How long, in seconds, between the starting and ending times of the build's phase.

        

        

      contexts -> (list)

        

        Additional information about a build phase, especially to help troubleshoot a failed build.

        

        (structure)

          

          Additional information about a build phase that has an error. You can use this information to help troubleshoot a failed build.

          

          statusCode -> (string)

            

            The status code for the context of the build phase.

            

            

          message -> (string)

            

            An explanation of the build phase's context. This explanation might include a command ID and an exit code.

            

            

          

        

      

    

  source -> (structure)

    

    Information about the source code to be built.

    

    type -> (string)

      

      The type of repository that contains the source code to be built. Valid values include:

       

       
      * ``CODECOMMIT`` : The source code is in an AWS CodeCommit repository. 
       
      * ``CODEPIPELINE`` : The source code settings are specified in the source action of a pipeline in AWS CodePipeline. 
       
      * ``GITHUB`` : The source code is in a GitHub repository. 
       
      * ``S3`` : The source code is in an Amazon Simple Storage Service (Amazon S3) input bucket. 
       

      

      

    location -> (string)

      

      Information about the location of the source code to be built. Valid values include:

       

       
      * For source code settings that are specified in the source action of a pipeline in AWS CodePipeline, ``location`` should not be specified. If it is specified, AWS CodePipeline will ignore it. This is because AWS CodePipeline uses the settings in a pipeline's source action instead of this value. 
       
      * For source code in an AWS CodeCommit repository, the HTTPS clone URL to the repository that contains the source code and the build spec (for example, ``https://git-codecommit.*region-ID* .amazonaws.com/v1/repos/*repo-name* `` ). 
       
      * For source code in an Amazon Simple Storage Service (Amazon S3) input bucket, the path to the ZIP file that contains the source code (for example, `` *bucket-name* /*path* /*to* /*object-name* .zip`` ) 
       
      * For source code in a GitHub repository, the HTTPS clone URL to the repository that contains the source and the build spec. Also, you must connect your AWS account to your GitHub account. To do this, use the AWS CodeBuild console to begin creating a build project. When you use the console to connect (or reconnect) with GitHub, on the GitHub **Authorize application** page that displays, for **Organization access** , choose **Request access** next to each repository you want to allow AWS CodeBuild to have access to. Then choose **Authorize application** . (After you have connected to your GitHub account, you do not need to finish creating the build project, and you may then leave the AWS CodeBuild console.) To instruct AWS CodeBuild to then use this connection, in the ``source`` object, set the ``auth`` object's ``type`` value to ``OAUTH`` . 
       

      

      

    buildspec -> (string)

      

      The build spec declaration to use for the builds in this build project.

       

      If this value is not specified, a build spec must be included along with the source code to be built.

      

      

    auth -> (structure)

      

      Information about the authorization settings for AWS CodeBuild to access the source code to be built.

       

      This information is for the AWS CodeBuild console's use only. Your code should not get or set this information directly (unless the build project's source ``type`` value is ``GITHUB`` ).

      

      type -> (string)

        

        The authorization type to use. The only valid value is ``OAUTH`` , which represents the OAuth authorization type.

        

        

      resource -> (string)

        

        The resource value that applies to the specified authorization type.

        

        

      

    

  artifacts -> (structure)

    

    Information about the output artifacts for the build.

    

    location -> (string)

      

      Information about the location of the build artifacts.

      

      

    sha256sum -> (string)

      

      The SHA-256 hash of the build artifact.

       

      You can use this hash along with a checksum tool to confirm both file integrity and authenticity.

       

      .. note::

         

        This value is available only if the build project's ``packaging`` value is set to ``ZIP`` .

         

      

      

    md5sum -> (string)

      

      The MD5 hash of the build artifact.

       

      You can use this hash along with a checksum tool to confirm both file integrity and authenticity.

       

      .. note::

         

        This value is available only if the build project's ``packaging`` value is set to ``ZIP`` .

         

      

      

    

  environment -> (structure)

    

    Information about the build environment for this build.

    

    type -> (string)

      

      The type of build environment to use for related builds.

      

      

    image -> (string)

      

      The ID of the Docker image to use for this build project.

      

      

    computeType -> (string)

      

      Information about the compute resources the build project will use. Available values include:

       

       
      * ``BUILD_GENERAL1_SMALL`` : Use up to 3 GB memory and 2 vCPUs for builds. 
       
      * ``BUILD_GENERAL1_MEDIUM`` : Use up to 7 GB memory and 4 vCPUs for builds. 
       
      * ``BUILD_GENERAL1_LARGE`` : Use up to 15 GB memory and 8 vCPUs for builds. 
       

      

      

    environmentVariables -> (list)

      

      A set of environment variables to make available to builds for this build project.

      

      (structure)

        

        Information about an environment variable for a build project or a build.

        

        name -> (string)

          

          The name or key of the environment variable.

          

          

        value -> (string)

          

          The value of the environment variable.

           

          .. warning::

             

            We strongly discourage using environment variables to store sensitive values, especially AWS secret key IDs and secret access keys. Environment variables can be displayed in plain text using tools such as the AWS CodeBuild console and the AWS Command Line Interface (AWS CLI).

             

          

          

        

      

    privilegedMode -> (boolean)

      

      If set to true, enables running the Docker daemon inside a Docker container; otherwise, false or not specified (the default). This value must be set to true only if this build project will be used to build Docker images, and the specified build environment image is not one provided by AWS CodeBuild with Docker support. Otherwise, all associated builds that attempt to interact with the Docker daemon will fail. Note that you must also start the Docker daemon so that your builds can interact with it as needed. One way to do this is to initialize the Docker daemon in the install phase of your build spec by running the following build commands. (Do not run the following build commands if the specified build environment image is provided by AWS CodeBuild with Docker support.)

       

       ``- nohup /usr/local/bin/dockerd --host=unix:///var/run/docker.sock --host=tcp://0.0.0.0:2375 --storage-driver=vfs- timeout -t 15 sh -c "until docker info; do echo .; sleep 1; done"``  

      

      

    

  logs -> (structure)

    

    Information about the build's logs in Amazon CloudWatch Logs.

    

    groupName -> (string)

      

      The name of the Amazon CloudWatch Logs group for the build logs.

      

      

    streamName -> (string)

      

      The name of the Amazon CloudWatch Logs stream for the build logs.

      

      

    deepLink -> (string)

      

      The URL to an individual build log in Amazon CloudWatch Logs.

      

      

    

  timeoutInMinutes -> (integer)

    

    How long, in minutes, for AWS CodeBuild to wait before timing out this build if it does not get marked as completed.

    

    

  buildComplete -> (boolean)

    

    Whether the build has finished. True if completed; otherwise, false.

    

    

  initiator -> (string)

    

    The entity that started the build. Valid values include:

     

     
    * If AWS CodePipeline started the build, the pipeline's name (for example, ``codepipeline/my-demo-pipeline`` ). 
     
    * If an AWS Identity and Access Management (IAM) user started the build, the user's name (for example ``MyUserName`` ). 
     
    * If the Jenkins plugin for AWS CodeBuild started the build, the string ``CodeBuild-Jenkins-Plugin`` . 
     

    

    

  

