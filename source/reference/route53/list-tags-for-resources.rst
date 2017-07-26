[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-tags-for-resources:


***********************
list-tags-for-resources
***********************



===========
Description
===========



========
Synopsis
========

::

    list-tags-for-resources
  --resource-type <value>
  --resource-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-type`` (string)


  The type of the resources.

   

  - The resource type for health checks is ``healthcheck`` .

   

  - The resource type for hosted zones is ``hostedzone`` .

  

  Possible values:

  
  *   ``healthcheck``

  
  *   ``hostedzone``

  

  

``--resource-ids`` (list)


  A complex type that contains the ResourceId element for each resource for which you want to get a list of tags.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ResourceTagSets -> (list)

  

  A list of ``ResourceTagSet`` s containing tags associated with the specified resources.

  

  (structure)

    

    A complex type containing a resource and its associated tags.

    

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

          

          

        

      

    

  

