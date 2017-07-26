[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift create-cluster-subnet-group:


***************************
create-cluster-subnet-group
***************************



===========
Description
===========



Creates a new Amazon Redshift subnet group. You must provide a list of one or more subnets in your existing Amazon Virtual Private Cloud (Amazon VPC) when creating Amazon Redshift subnet group. 

 

For information about subnet groups, go to `Amazon Redshift Cluster Subnet Groups`_ in the *Amazon Redshift Cluster Management Guide* . 



========
Synopsis
========

::

    create-cluster-subnet-group
  --cluster-subnet-group-name <value>
  --description <value>
  --subnet-ids <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-subnet-group-name`` (string)


  The name for the subnet group. Amazon Redshift stores the value as a lowercase string. 

   

  Constraints: 

   

   
  * Must contain no more than 255 alphanumeric characters or hyphens.
   
  * Must not be "Default".
   
  * Must be unique for all subnet groups that are created by your AWS account.
   

   

  Example: ``examplesubnetgroup`` 

  

``--description`` (string)


  A description for the subnet group.

  

``--subnet-ids`` (list)


  An array of VPC subnet IDs. A maximum of 20 subnets can be modified in a single request. 

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  A list of tag instances.

  



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



========
Examples
========

Create a Cluster Subnet Group
-----------------------------

This example creates a new cluster subnet group.

Command::

   aws redshift create-cluster-subnet-group --cluster-subnet-group-name mysubnetgroup  --description "My subnet group" --subnet-ids subnet-763fdd1c

Result::

    {
       "ClusterSubnetGroup": {
          "Subnets": [
             {
                "SubnetStatus": "Active",
                "SubnetIdentifier": "subnet-763fdd1c",
                "SubnetAvailabilityZone": {
                   "Name": "us-east-1a"
                }
             } ],
          "VpcId": "vpc-7e3fdd14",
          "SubnetGroupStatus": "Complete",
          "Description": "My subnet group",
          "ClusterSubnetGroupName": "mysubnetgroup"
       },
       "ResponseMetadata": {
          "RequestId": "500b8ce2-698f-11e2-9790-fd67517fb6fd"
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

        

        

      

    

  



.. _Amazon Redshift Cluster Subnet Groups: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-cluster-subnet-groups.html
