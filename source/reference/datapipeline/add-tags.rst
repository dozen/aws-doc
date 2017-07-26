[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline add-tags:


********
add-tags
********



===========
Description
===========



Adds or modifies tags for the specified pipeline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/datapipeline-2012-10-29/AddTags>`_


========
Synopsis
========

::

    add-tags
  --pipeline-id <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline.

  

``--tags`` (list)


  The tags to add, as key/value pairs.

  



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
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add a tag to a pipeline**

This example adds the specified tag to the specified pipeline::

   aws datapipeline add-tags --pipeline-id df-00627471SOVYZEXAMPLE --tags key=environment,value=production key=owner,value=sales
   
To view the tags, use the describe-pipelines command. For example, the tags added in the example command appear as follows in the output for describe-pipelines::

  {
      ...
          "tags": [
              {
                  "value": "production",
                  "key": "environment"
              },
              {
                  "value": "sales",
                  "key": "owner"
              }
          ]
      ...
  }


======
Output
======

