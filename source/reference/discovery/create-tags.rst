[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery create-tags:


***********
create-tags
***********



===========
Description
===========



Creates one or more tags for configuration items. Tags are metadata that help you categorize IT assets. This API accepts a list of multiple configuration items.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/CreateTags>`_


========
Synopsis
========

::

    create-tags
  --configuration-ids <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-ids`` (list)


  A list of configuration items that you want to tag.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  Tags that you want to associate with one or more configuration items. Specify the tags that you want to create in a *key* -*value* format. For example:

   

   ``{"key": "serverType", "value": "webServer"}``  

  



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



======
Output
======

