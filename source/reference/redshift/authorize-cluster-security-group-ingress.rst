[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift authorize-cluster-security-group-ingress:


****************************************
authorize-cluster-security-group-ingress
****************************************



===========
Description
===========



Adds an inbound (ingress) rule to an Amazon Redshift security group. Depending on whether the application accessing your cluster is running on the Internet or an EC2 instance, you can authorize inbound access to either a Classless Interdomain Routing (CIDR) IP address range or an EC2 security group. You can add as many as 20 ingress rules to an Amazon Redshift security group. 

 

.. note::

  The EC2 security group must be defined in the AWS region where the cluster resides. 

 

For an overview of CIDR blocks, see the Wikipedia article on `Classless Inter-Domain Routing`_ . 

 

You must also associate the security group with a cluster so that clients running on these IP addresses or the EC2 instance are authorized to connect to the cluster. For information about managing security groups, go to `Working with Security Groups`_ in the *Amazon Redshift Cluster Management Guide* .



========
Synopsis
========

::

    authorize-cluster-security-group-ingress
  --cluster-security-group-name <value>
  [--cidrip <value>]
  [--ec2-security-group-name <value>]
  [--ec2-security-group-owner-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-security-group-name`` (string)


  The name of the security group to which the ingress rule is added. 

  

``--cidrip`` (string)


  The IP range to be added the Amazon Redshift security group. 

  

``--ec2-security-group-name`` (string)


  The EC2 security group to be added the Amazon Redshift security group. 

  

``--ec2-security-group-owner-id`` (string)


  The AWS account number of the owner of the security group specified by the *EC2SecurityGroupName* parameter. The AWS Access Key ID is not an acceptable value. 

   

  Example: ``111122223333``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Authorizing Access to an EC2 Security Group
-------------------------------------------

This example authorizes access to a named Amazon EC2 security group.

Command::

   aws redshift authorize-cluster-security-group-ingress --cluster-security-group-name mysecuritygroup --ec2-security-group-name myec2securitygroup --ec2-security-group-owner-id 123445677890

Authorizing Access to a CIDR range
----------------------------------

This example authorizes access to a CIDR range.

Command::

   aws redshift authorize-cluster-security-group-ingress --cluster-security-group-name mysecuritygroup --cidrip 192.168.100.100/32




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

        

        

      

    

  



.. _Classless Inter-Domain Routing: http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing
.. _Working with Security Groups: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-security-groups.html
