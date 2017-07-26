[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds authorize-db-security-group-ingress:


***********************************
authorize-db-security-group-ingress
***********************************



===========
Description
===========



Enables ingress to a DBSecurityGroup using one of two forms of authorization. First, EC2 or VPC security groups can be added to the DBSecurityGroup if the application using the database is running on EC2 or VPC instances. Second, IP ranges are available if the application accessing your database is running on the Internet. Required parameters for this API are one of CIDR range, EC2SecurityGroupId for VPC, or (EC2SecurityGroupOwnerId and either EC2SecurityGroupName or EC2SecurityGroupId for non-VPC).

 

.. note::

   

  You cannot authorize ingress from an EC2 security group in one region to an Amazon RDS DB instance in another. You cannot authorize ingress from a VPC security group in one VPC to an Amazon RDS DB instance in another.

   

 

For an overview of CIDR ranges, go to the `Wikipedia Tutorial <http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/AuthorizeDBSecurityGroupIngress>`_


========
Synopsis
========

::

    authorize-db-security-group-ingress
  --db-security-group-name <value>
  [--cidrip <value>]
  [--ec2-security-group-name <value>]
  [--ec2-security-group-id <value>]
  [--ec2-security-group-owner-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-security-group-name`` (string)


  The name of the DB security group to add authorization to.

  

``--cidrip`` (string)


  The IP range to authorize.

  

``--ec2-security-group-name`` (string)


  Name of the EC2 security group to authorize. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, ``EC2SecurityGroupOwnerId`` and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

  

``--ec2-security-group-id`` (string)


  Id of the EC2 security group to authorize. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, ``EC2SecurityGroupOwnerId`` and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

  

``--ec2-security-group-owner-id`` (string)


  AWS account number of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` parameter. The AWS Access Key ID is not an acceptable value. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, ``EC2SecurityGroupOwnerId`` and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DBSecurityGroup -> (structure)

  

  Contains the result of a successful invocation of the following actions:

   

   
  *  describe-db-security-groups   
   
  *  authorize-db-security-group-ingress   
   
  *  create-db-security-group   
   
  *  revoke-db-security-group-ingress   
   

   

  This data type is used as a response element in the  describe-db-security-groups action.

  

  OwnerId -> (string)

    

    Provides the AWS ID of the owner of a specific DB security group.

    

    

  DBSecurityGroupName -> (string)

    

    Specifies the name of the DB security group.

    

    

  DBSecurityGroupDescription -> (string)

    

    Provides the description of the DB security group.

    

    

  VpcId -> (string)

    

    Provides the VpcId of the DB security group.

    

    

  EC2SecurityGroups -> (list)

    

    Contains a list of  EC2SecurityGroup elements. 

    

    (structure)

      

      This data type is used as a response element in the following actions:

       

       
      *  authorize-db-security-group-ingress   
       
      *  describe-db-security-groups   
       
      *  revoke-db-security-group-ingress   
       

      

      Status -> (string)

        

        Provides the status of the EC2 security group. Status can be "authorizing", "authorized", "revoking", and "revoked".

        

        

      EC2SecurityGroupName -> (string)

        

        Specifies the name of the EC2 security group.

        

        

      EC2SecurityGroupId -> (string)

        

        Specifies the id of the EC2 security group.

        

        

      EC2SecurityGroupOwnerId -> (string)

        

        Specifies the AWS ID of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` field. 

        

        

      

    

  IPRanges -> (list)

    

    Contains a list of  IPRange elements. 

    

    (structure)

      

      This data type is used as a response element in the  describe-db-security-groups action. 

      

      Status -> (string)

        

        Specifies the status of the IP range. Status can be "authorizing", "authorized", "revoking", and "revoked".

        

        

      CIDRIP -> (string)

        

        Specifies the IP range.

        

        

      

    

  DBSecurityGroupArn -> (string)

    

    The Amazon Resource Name (ARN) for the DB security group.

    

    

  

