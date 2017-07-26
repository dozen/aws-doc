[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 change-tags-for-resource:


************************
change-tags-for-resource
************************



===========
Description
===========



Adds, edits, or deletes tags for a health check or a hosted zone.

 

For information about using tags for cost allocation, see `Using Cost Allocation Tags <http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html>`_ in the *AWS Billing and Cost Management User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ChangeTagsForResource>`_


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


  The ID of the resource for which you want to add, change, or delete tags.

  

``--add-tags`` (list)


  A complex type that contains a list of the tags that you want to add to the specified health check or hosted zone and/or the tags that you want to edit ``Value`` for.

   

  You can add a maximum of 10 tags to a health check or a hosted zone.

  



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


  A complex type that contains a list of the tags that you want to delete from the specified health check or hosted zone. You can specify up to 10 keys.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command adds a tag named ``owner`` to a healthcheck resource specified by ID::

  aws route53 change-tags-for-resource --resource-type healthcheck --resource-id 6233434j-18c1-34433-ba8e-3443434 --add-tags Key=owner,Value=myboss

The following command removes a tag named ``owner`` from a hosted zone resource specified by ID::

  aws route53 change-tags-for-resource --resource-type hostedzone --resource-id Z1523434445 --remove-tag-keys owner 


======
Output
======

