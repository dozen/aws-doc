[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 change-tags-for-resource:


************************
change-tags-for-resource
************************



===========
Description
===========



========
Synopsis
========

::

    change-tags-for-resource
  --resource-type <value>
  --resource-id <value>
  [--add-tags <value>]
  [--remove-tag-keys <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-type`` (string)


  The type of the resource.

   

  - The resource type for health checks is ``healthcheck`` .

   

  - The resource type for hosted zones is ``hostedzone`` .

  

  Possible values:

  
  *   ``healthcheck``

  
  *   ``hostedzone``

  

  

``--resource-id`` (string)


  The ID of the resource for which you want to add, change, or delete tags.

  

``--add-tags`` (list)


  A complex type that contains a list of ``Tag`` elements. Each ``Tag`` element identifies a tag that you want to add or update for the specified resource.

  



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



``--remove-tag-keys`` (list)


  A list of ``Tag`` keys that you want to remove from the specified resource.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

