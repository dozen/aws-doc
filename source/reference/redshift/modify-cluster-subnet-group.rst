[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift modify-cluster-subnet-group:


***************************
modify-cluster-subnet-group
***************************



===========
Description
===========



Modifies a cluster subnet group to include the specified list of VPC subnets. The operation replaces the existing list of subnets with the new list of subnets. 



========
Synopsis
========

::

    modify-cluster-subnet-group
  --cluster-subnet-group-name <value>
  [--description <value>]
  --subnet-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-subnet-group-name`` (string)


  The name of the subnet group to be modified.

  

``--description`` (string)


  A text description of the subnet group to be modified.

  

``--subnet-ids`` (list)


  An array of VPC subnet IDs. A maximum of 20 subnets can be modified in a single request. 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Modify the Subnets in a Cluster Subnet Group
--------------------------------------------

This example shows how to modify the list of subnets in a cache subnet group.  By default, the output is in JSON format.

Command::

   aws redshift modify-cluster-subnet-group --cluster-subnet-group-name mysubnetgroup --subnet-ids subnet-763fdd1 subnet-ac830e9

Result::

    {
       "ClusterSubnetGroup":
       {
          "Subnets": [
             {
                "SubnetStatus": "Active",
                "SubnetIdentifier": "subnet-763fdd1c",
                "SubnetAvailabilityZone":
                   { "Name": "us-east-1a" }
             },
             {
                "SubnetStatus": "Active",
                "SubnetIdentifier": "subnet-ac830e9",
                "SubnetAvailabilityZone":
                   { "Name": "us-east-1b" }
             } ],
          "VpcId": "vpc-7e3fdd14",
          "SubnetGroupStatus": "Complete",
          "Description": "My subnet group",
          "ClusterSubnetGroupName": "mysubnetgroup"
       },
       "ResponseMetadata": {
          "RequestId": "8da93e89-8372-f936-93a8-873918938197a"
       }
    }



======
Output
======

ClusterSubnetGroup -> (structure)

  

  Describes a subnet group.

  

  ClusterSubnetGroupName -> (string)

    

    The name of the cluster subnet group. 

    

    

  Description -> (string)

    

    The description of the cluster subnet group. 

    

    

  VpcId -> (string)

    

    The VPC ID of the cluster subnet group. 

    

    

  SubnetGroupStatus -> (string)

    

    The status of the cluster subnet group. Possible values are ``Complete`` , ``Incomplete`` and ``Invalid`` . 

    

    

  Subnets -> (list)

    

    A list of the VPC  Subnet elements. 

    

    (structure)

      

      Describes a subnet. 

      

      SubnetIdentifier -> (string)

        

        The identifier of the subnet. 

        

        

      SubnetAvailabilityZone -> (structure)

        

        Describes an availability zone. 

        

        Name -> (string)

          

          The name of the availability zone. 

          

          

        

      SubnetStatus -> (string)

        

        The status of the subnet. 

        

        

      

    

  Tags -> (list)

    

    The list of tags for the cluster subnet group.

    

    (structure)

      

      A tag consisting of a name/value pair for a resource.

      

      Key -> (string)

        

        The key, or name, for the resource tag.

        

        

      Value -> (string)

        

        The value for the resource tag.

        

        

      

    

  

