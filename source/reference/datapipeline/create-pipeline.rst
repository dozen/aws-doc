[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline create-pipeline:


***************
create-pipeline
***************



===========
Description
===========



Creates a new, empty pipeline. Use  put-pipeline-definition to populate the pipeline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/datapipeline-2012-10-29/CreatePipeline>`_


========
Synopsis
========

::

    create-pipeline
  --name <value>
  --unique-id <value>
  [--description <value>]
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name for the pipeline. You can use the same name for multiple pipelines associated with your AWS account, because AWS Data Pipeline assigns each pipeline a unique pipeline identifier.

  

``--unique-id`` (string)


  A unique identifier. This identifier is not the same as the pipeline identifier assigned by AWS Data Pipeline. You are responsible for defining the format and ensuring the uniqueness of this identifier. You use this parameter to ensure idempotency during repeated calls to ``create-pipeline`` . For example, if the first call to ``create-pipeline`` does not succeed, you can pass in the same unique identifier and pipeline name combination on a subsequent call to ``create-pipeline`` . ``create-pipeline`` ensures that if a pipeline already exists with the same name and unique identifier, a new pipeline is not created. Instead, you'll receive the pipeline identifier from the previous attempt. The uniqueness of the name and unique identifier combination is scoped to the AWS account or IAM user credentials.

  

``--description`` (string)


  The description for the pipeline.

  

``--tags`` (list)


  A list of tags to associate with the pipeline at creation. Tags let you control access to pipelines. For more information, see `Controlling User Access to Pipelines <http://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-control-access.html>`_ in the *AWS Data Pipeline Developer Guide* .

  



Shorthand Syntax::

    key=string,value=string ...




JSON Syntax::

  [
    {
      "key": "string",
      "value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON description provided. The JSON description follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a pipeline**

This example creates a pipeline::

   aws datapipeline create-pipeline --name my-pipeline --unique-id my-pipeline-token
   
The following is example output::

  {
      "pipelineId": "df-00627471SOVYZEXAMPLE"
  }


======
Output
======

pipelineId -> (string)

  

  The ID that AWS Data Pipeline assigns the newly created pipeline. For example, ``df-06372391ZG65EXAMPLE`` .

  

  

