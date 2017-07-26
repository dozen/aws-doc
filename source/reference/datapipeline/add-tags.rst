[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline add-tags:


********
add-tags
********



===========
Description
===========



Adds or modifies tags for the specified pipeline.



========
Synopsis
========

::

    add-tags
  --pipeline-id <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

