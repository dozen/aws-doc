[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail remove-tags:


***********
remove-tags
***********



===========
Description
===========



Removes the specified tags from a trail.



========
Synopsis
========

::

    remove-tags
  --resource-id <value>
  [--tags-list <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-id`` (string)


  Specifies the ARN of the trail from which tags should be removed. The format of a trail ARN is ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail`` .

  

``--tags-list`` (list)


  Specifies a list of tags to be removed. 

  



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

