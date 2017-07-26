[ :ref:`aws <cli:aws>` ]

.. _cli:aws codepipeline:


************
codepipeline
************



===========
Description
===========

 **Overview**  

This is the AWS CodePipeline API Reference. This guide provides descriptions of the actions and data types for AWS CodePipeline. Some functionality for your pipeline is only configurable through the API. For additional information, see the `AWS CodePipeline User Guide`_ .

 

You can use the AWS CodePipeline API to work with pipelines, stages, actions, gates, and transitions, as described below.

 

*Pipelines* are models of automated release processes. Each pipeline is uniquely named, and consists of actions, gates, and stages. 

 

You can work with pipelines by calling: 

 
*  create-pipeline , which creates a uniquely-named pipeline.
 
*  delete-pipeline , which deletes the specified pipeline.
 
*  get-pipeline , which returns information about a pipeline structure.
 
*  get-pipeline-state , which returns information about the current state of the stages and actions of a pipeline.
 
*  list-pipelines , which gets a summary of all of the pipelines associated with your account.
 
*  start-pipeline-execution , which runs the the most recent revision of an artifact through the pipeline.
 
*  update-pipeline , which updates a pipeline with edits or changes to the structure of the pipeline.
 

 

Pipelines include *stages* , which are which are logical groupings of gates and actions. Each stage contains one or more actions that must complete before the next stage begins. A stage will result in success or failure. If a stage fails, then the pipeline stops at that stage and will remain stopped until either a new version of an artifact appears in the source location, or a user takes action to re-run the most recent artifact through the pipeline. You can call  get-pipeline-state , which displays the status of a pipeline, including the status of stages in the pipeline, or  get-pipeline , which returns the entire structure of the pipeline, including the stages of that pipeline. For more information about the structure of stages and actions, also refer to the AWS CodePipeline Pipeline Structure Reference.

 

 

Pipeline stages include *actions* , which are categorized into categories such as source or build actions performed within a stage of a pipeline. For example, you can use a source action to import artifacts into a pipeline from a source such as Amazon S3. Like stages, you do not work with actions directly in most cases, but you do define and interact with actions when working with pipeline operations such as  create-pipeline and  get-pipeline-state . 

 

Pipelines also include *transitions* , which allow the transition of artifacts from one stage to the next in a pipeline after the actions in one stage complete.

 

You can work with transitions by calling:

 

 
*  disable-stage-transition , which prevents artifacts from transitioning to the next stage in a pipeline.
 
*  enable-stage-transition , which enables transition of artifacts between stages in a pipeline. 
 

 

**Using the API to integrate with AWS CodePipeline** 

 

For third-party integrators or developers who want to create their own integrations with AWS CodePipeline, the expected sequence varies from the standard API user. In order to integrate with AWS CodePipeline, developers will need to work with the following items:

 

 
* Jobs, which are instances of an action. For example, a job for a source action might import a revision of an artifact from a source. You can work with jobs by calling: 

   
  *  acknowledge-job , which confirms whether a job worker has received the specified job,
   
  *  get-job-details , which returns the details of a job,
   
  *  poll-for-jobs , which determines whether there are any jobs to act upon, 
   
  *  put-job-failure-result , which provides details of a job failure, and
   
  *  put-job-success-result , which provides details of a job success.
   

 
 
* Third party jobs, which are instances of an action created by a partner action and integrated into AWS CodePipeline. Partner actions are created by members of the AWS Partner Network. You can work with third party jobs by calling: 

   
  *  acknowledge-third-party-job , which confirms whether a job worker has received the specified job,
   
  *  get-third-party-job-details , which requests the details of a job for a partner action,
   
  *  poll-for-third-party-jobs , which determines whether there are any jobs to act upon, 
   
  *  put-third-party-job-failure-result , which provides details of a job failure, and
   
  *  put-third-party-job-success-result , which provides details of a job success.
   

 
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  acknowledge-job
  acknowledge-third-party-job
  create-custom-action-type
  create-pipeline
  delete-custom-action-type
  delete-pipeline
  disable-stage-transition
  enable-stage-transition
  get-job-details
  get-pipeline
  get-pipeline-state
  get-third-party-job-details
  list-action-types
  list-pipelines
  poll-for-jobs
  poll-for-third-party-jobs
  put-action-revision
  put-job-failure-result
  put-job-success-result
  put-third-party-job-failure-result
  put-third-party-job-success-result
  start-pipeline-execution
  update-pipeline


.. _AWS CodePipeline User Guide: http://docs.aws.amazon.com/pipelines/latest/userguide/welcome.html
