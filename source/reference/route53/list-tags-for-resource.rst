[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



========
Synopsis
========

::

    list-tags-for-resource
  --resource-type <value>
  --resource-id <value>
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


  The ID of the resource for which you want to retrieve tags.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ResourceTagSet -> (structure)

  

  A ``ResourceTagSet`` containing tags associated with the specified resource.

  

  ResourceType -> (string)

    

    The type of the resource.

     

    - The resource type for health checks is ``healthcheck`` .

     

    - The resource type for hosted zones is ``hostedzone`` .

    

    

  ResourceId -> (string)

    

    The ID for the specified resource.

    

    

  Tags -> (list)

    

    The tags associated with the specified resource.

    

    (structure)

      

      A single tag containing a key and value.

      

      Key -> (string)

        

        The key for a ``Tag`` .

        

        

      Value -> (string)

        

        The value for a ``Tag`` .

        

        

      

    

  

