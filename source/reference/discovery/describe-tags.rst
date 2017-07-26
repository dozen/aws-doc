[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery describe-tags:


*************
describe-tags
*************



===========
Description
===========



Retrieves a list of configuration items that are tagged with a specific tag. Or retrieves a list of all tags assigned to a specific configuration item.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/DescribeTags>`_


========
Synopsis
========

::

    describe-tags
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  You can filter the list using a *key* -*value* format. You can separate these items by using logical operators. Allowed filters include ``tagKey`` , ``tagValue`` , and ``configurationId`` . 

  



Shorthand Syntax::

    name=string,values=string,string ...




JSON Syntax::

  [
    {
      "name": "string",
      "values": ["string", ...]
    }
    ...
  ]



``--max-results`` (integer)


  The total number of items to return in a single page of output. The maximum value is 100.

  

``--next-token`` (string)


  A token to start the list. Use this token to get the next set of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

tags -> (list)

  

  Depending on the input, this is a list of configuration items tagged with a specific tag, or a list of tags for a specific configuration item.

  

  (structure)

    

    Tags for a configuration item. Tags are metadata that help you categorize IT assets.

    

    configurationType -> (string)

      

      A type of IT asset to tag.

      

      

    configurationId -> (string)

      

      The configuration ID for the item to tag. You can specify a list of keys and values.

      

      

    key -> (string)

      

      A type of tag on which to filter. For example, *serverType* .

      

      

    value -> (string)

      

      A value on which to filter. For example *key = serverType* and *value = web server* .

      

      

    timeOfCreation -> (timestamp)

      

      The time the configuration tag was created in Coordinated Universal Time (UTC).

      

      

    

  

nextToken -> (string)

  

  The call returns a token. Use this token to get the next set of results.

  

  

