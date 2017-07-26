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



========
Synopsis
========

::

    create-tags
  --resource-name <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None