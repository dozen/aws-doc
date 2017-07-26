[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift create-tags:


***********
create-tags
***********



===========
Description
===========



Adds one or more tags to a specified resource.

 

A resource can have up to 10 tags. If you try to create more than 10 tags for a resource, you will receive an error and the attempt will fail.

 

If you specify a key that already exists for the resource, the value for that key will be updated with the new value.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/CreateTags>`_


========
Synopsis
========

::

    create-tags
  --resource-name <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-name`` (string)


  The Amazon Resource Name (ARN) to which you want to add the tag or tags. For example, ``arn:aws:redshift:us-east-1:123456789:cluster:t1`` . 

  

``--tags`` (list)


  One or more name/value pairs to add as tags to the specified resource. Each tag name is passed in with the parameter ``Key`` and the corresponding value is passed in with the parameter ``Value`` . The ``Key`` and ``Value`` parameters are separated by a comma (,). Separate multiple tags with a space. For example, ``--tags "Key"="owner","Value"="admin" "Key"="environment","Value"="test" "Key"="version","Value"="1.0"`` . 

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
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

None