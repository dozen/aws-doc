[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery delete-tags:


***********
delete-tags
***********



===========
Description
===========



Deletes the association between configuration items and one or more tags. This API accepts a list of multiple configuration items.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/DeleteTags>`_


========
Synopsis
========

::

    delete-tags
  --configuration-ids <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-ids`` (list)


  A list of configuration items with tags that you want to delete.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  Tags that you want to delete from one or more configuration items. Specify the tags that you want to delete in a *key* -*value* format. For example:

   

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

