[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift create-cluster-security-group:


*****************************
create-cluster-security-group
*****************************



===========
Description
===========



Creates a new Amazon Redshift security group. You use security groups to control access to non-VPC clusters.

 

For information about managing security groups, go to `Amazon Redshift Cluster Security Groups <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-security-groups.html>`_ in the *Amazon Redshift Cluster Management Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/CreateClusterSecurityGroup>`_


========
Synopsis
========

::

    create-cluster-security-group
  --cluster-security-group-name <value>
  --description <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-security-group-name`` (string)


  The name for the security group. Amazon Redshift stores the value as a lowercase string.

   

  Constraints:

   

   
  * Must contain no more than 255 alphanumeric characters or hyphens. 
   
  * Must not be "Default". 
   
  * Must be unique for all security groups that are created by your AWS account. 
   

   

  Example: ``examplesecuritygroup``  

  

``--description`` (string)


  A description for the security group.

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

Creating a Cluster Security Group
---------------------------------

This example creates a new cluster security group. By default, the output is in JSON format.

Command::

   aws redshift create-cluster-security-group --cluster-security-group-name mysecuritygroup --description "This is my cluster security group"

Result::

    {
       "create_cluster_security_group_response": {
          "create_cluster_security_group_result": {
             "cluster_security_group": {
                "description": "This is my cluster security group",
                "owner_id": "300454760768",
                "cluster_security_group_name": "mysecuritygroup",
                "ec2_security_groups": \[],
                "ip_ranges": \[]
             }
          },
          "response_metadata": {
             "request_id": "5df486a0-343a-11e2-b0d8-d15d0ef48549"
          }
       }
    }

You can also obtain the same information in text format using the ``--output text`` option.

Command::

   aws redshift create-cluster-security-group --cluster-security-group-name mysecuritygroup --description "This is my cluster security group" --output text

Result::

    This is my cluster security group	300454760768	mysecuritygroup
    a0c0bfab-343a-11e2-95d2-c3dc9fe8ab57




======
Output
======

ClusterSecurityGroup -> (structure)

  

  Describes a security group.

  

  ClusterSecurityGroupName -> (string)

    

    The name of the cluster security group to which the operation was applied.

    

    

  Description -> (string)

    

    A description of the security group.

    

    

  EC2SecurityGroups -> (list)

    

    A list of EC2 security groups that are permitted to access clusters associated with this cluster security group.

    

    (structure)

      

      Describes an Amazon EC2 security group.

      

      Status -> (string)

        

        The status of the EC2 security group.

        

        

      EC2SecurityGroupName -> (string)

        

        The name of the EC2 Security Group.

        

        

      EC2SecurityGroupOwnerId -> (string)

        

        The AWS ID of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` field. 

        

        

      Tags -> (list)

        

        The list of tags for the EC2 security group.

        

        (structure)

          

          A tag consisting of a name/value pair for a resource.

          

          Key -> (string)

            

            The key, or name, for the resource tag.

            

            

          Value -> (string)

            

            The value for the resource tag.

            

            

          

        

      

    

  IPRanges -> (list)

    

    A list of IP ranges (CIDR blocks) that are permitted to access clusters associated with this cluster security group.

    

    (structure)

      

      Describes an IP range used in a security group.

      

      Status -> (string)

        

        The status of the IP range, for example, "authorized".

        

        

      CIDRIP -> (string)

        

        The IP range in Classless Inter-Domain Routing (CIDR) notation.

        

        

      Tags -> (list)

        

        The list of tags for the IP range.

        

        (structure)

          

          A tag consisting of a name/value pair for a resource.

          

          Key -> (string)

            

            The key, or name, for the resource tag.

            

            

          Value -> (string)

            

            The value for the resource tag.

            

            

          

        

      

    

  Tags -> (list)

    

    The list of tags for the cluster security group.

    

    (structure)

      

      A tag consisting of a name/value pair for a resource.

      

      Key -> (string)

        

        The key, or name, for the resource tag.

        

        

      Value -> (string)

        

        The value for the resource tag.

        

        

      

    

  

