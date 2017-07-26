[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail add-tags:


********
add-tags
********



===========
Description
===========



Adds one or more tags to a trail, up to a limit of 10. Tags must be unique per trail. Overwrites an existing tag's value when a new value is specified for an existing tag key. If you specify a key without a value, the tag will be created with the specified key and a value of null. You can tag a trail that applies to all regions only from the region in which the trail was created (that is, from its home region).



========
Synopsis
========

::

    add-tags
  --resource-id <value>
  [--tags-list <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-id`` (string)


  Specifies the ARN of the trail to which one or more tags will be added. The format of a trail ARN is ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail`` .

  

``--tags-list`` (list)


  Contains a list of CloudTrail tags, up to a limit of 10.

  



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

