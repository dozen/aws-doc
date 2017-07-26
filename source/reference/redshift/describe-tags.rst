[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-tags:


*************
describe-tags
*************



===========
Description
===========



Returns a list of tags. You can return tags from a specific resource by specifying an ARN, or you can return all tags for a given type of resource, such as clusters, snapshots, and so on.

 

The following are limitations for ``describe-tags`` : 

 
* You cannot specify an ARN and a resource-type value together in the same request.
 
* You cannot use the ``MaxRecords`` and ``Marker`` parameters together with the ARN parameter.
 
* The ``MaxRecords`` parameter can be a range from 10 to 50 results to return in a request.
 

 

 

If you specify both tag keys and tag values in the same request, Amazon Redshift returns all resources that match any combination of the specified keys and values. For example, if you have ``owner`` and ``environment`` for tag keys, and ``admin`` and ``test`` for tag values, all resources that have any combination of those values are returned.

 

If both tag keys and values are omitted from the request, resources are returned regardless of whether they have tag keys or values associated with them.



========
Synopsis
========

::

    describe-tags
  [--resource-name <value>]
  [--resource-type <value>]
  [--max-records <value>]
  [--marker <value>]
  [--tag-keys <value>]
  [--tag-values <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-name`` (string)


  The Amazon Resource Name (ARN) for which you want to describe the tag or tags. For example, ``arn:aws:redshift:us-east-1:123456789:cluster:t1`` . 

  

``--resource-type`` (string)


  The type of resource with which you want to view tags. Valid resource types are: 

   
  * Cluster
   
  * CIDR/IP
   
  * EC2 security group
   
  * Snapshot
   
  * Cluster security group
   
  * Subnet group
   
  * HSM connection
   
  * HSM certificate
   
  * Parameter group
   
  * Snapshot copy grant
   

   

   

  For more information about Amazon Redshift resource types and constructing ARNs, go to `Constructing an Amazon Redshift Amazon Resource Name (ARN)`_ in the Amazon Redshift Cluster Management Guide. 

  

``--max-records`` (integer)


  The maximum number or response records to return in each call. If the number of remaining response records exceeds the specified ``MaxRecords`` value, a value is returned in a ``marker`` field of the response. You can retrieve the next set of records by retrying the command with the returned ``marker`` value. 

  

``--marker`` (string)


  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``marker`` parameter and retrying the command. If the ``marker`` field is empty, all response records have been retrieved for the request. 

  

``--tag-keys`` (list)


  A tag key or keys for which you want to return all matching resources that are associated with the specified key or keys. For example, suppose that you have resources tagged with keys called ``owner`` and ``environment`` . If you specify both of these tag keys in the request, Amazon Redshift returns a response with all resources that have either or both of these tag keys associated with them.

  



Syntax::

  "string" "string" ...



``--tag-values`` (list)


  A tag value or values for which you want to return all matching resources that are associated with the specified value or values. For example, suppose that you have resources tagged with values called ``admin`` and ``test`` . If you specify both of these tag values in the request, Amazon Redshift returns a response with all resources that have either or both of these tag values associated with them.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TaggedResources -> (list)

  

  A list of tags with their associated resources. 

  

  (structure)

    

    A tag and its associated resource. 

    

    Tag -> (structure)

      

      The tag for the resource. 

      

      Key -> (string)

        

        The key, or name, for the resource tag.

        

        

      Value -> (string)

        

        The value for the resource tag.

        

        

      

    ResourceName -> (string)

      

      The Amazon Resource Name (ARN) with which the tag is associated. For example, ``arn:aws:redshift:us-east-1:123456789:cluster:t1`` .

      

      

    ResourceType -> (string)

      

      The type of resource with which the tag is associated. Valid resource types are: 

       
      * Cluster
       
      * CIDR/IP
       
      * EC2 security group
       
      * Snapshot
       
      * Cluster security group
       
      * Subnet group
       
      * HSM connection
       
      * HSM certificate
       
      * Parameter group
       

       

       

      For more information about Amazon Redshift resource types and constructing ARNs, go to `Constructing an Amazon Redshift Amazon Resource Name (ARN)`_ in the Amazon Redshift Cluster Management Guide. 

      

      

    

  

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  



.. _Constructing an Amazon Redshift Amazon Resource Name (ARN): http://docs.aws.amazon.com/redshift/latest/mgmt/constructing-redshift-arn.html
