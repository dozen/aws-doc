[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



Lists tags for one health check or hosted zone. 

 

For information about using tags for cost allocation, see `Using Cost Allocation Tags <http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html>`_ in the *AWS Billing and Cost Management User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ListTagsForResource>`_


========
Synopsis
========

::

    list-tags-for-resource
  --resource-type <value>
  --resource-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-type`` (string)


  The type of the resource.

   

   
  * The resource type for health checks is ``healthcheck`` . 
   
  * The resource type for hosted zones is ``hostedzone`` . 
   

  

  Possible values:

  
  *   ``healthcheck``

  
  *   ``hostedzone``

  

  

``--resource-id`` (string)


  The ID of the resource for which you want to retrieve tags.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ResourceTagSet -> (structure)

  

  A ``ResourceTagSet`` containing tags associated with the specified resource.

  

  ResourceType -> (string)

    

    The type of the resource.

     

     
    * The resource type for health checks is ``healthcheck`` . 
     
    * The resource type for hosted zones is ``hostedzone`` . 
     

    

    

  ResourceId -> (string)

    

    The ID for the specified resource.

    

    

  Tags -> (list)

    

    The tags associated with the specified resource.

    

    (structure)

      

      A complex type that contains information about a tag that you want to add or edit for the specified health check or hosted zone.

      

      Key -> (string)

        

        The value of ``Key`` depends on the operation that you want to perform:

         

         
        * **Add a tag to a health check or hosted zone** : ``Key`` is the name that you want to give the new tag. 
         
        * **Edit a tag** : ``Key`` is the name of the tag that you want to change the ``Value`` for. 
         
        * **Delete a key** : ``Key`` is the name of the tag you want to remove. 
         
        * **Give a name to a health check** : Edit the default ``Name`` tag. In the Amazon Route 53 console, the list of your health checks includes a **Name** column that lets you see the name that you've given to each health check. 
         

        

        

      Value -> (string)

        

        The value of ``Value`` depends on the operation that you want to perform:

         

         
        * **Add a tag to a health check or hosted zone** : ``Value`` is the value that you want to give the new tag. 
         
        * **Edit a tag** : ``Value`` is the new value that you want to assign the tag. 
         

        

        

      

    

  

