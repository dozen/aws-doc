[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds revoke-db-security-group-ingress:


********************************
revoke-db-security-group-ingress
********************************



===========
Description
===========



Revokes ingress from a DBSecurityGroup for previously authorized IP ranges or EC2 or VPC Security Groups. Required parameters for this API are one of CIDRIP, EC2SecurityGroupId for VPC, or (EC2SecurityGroupOwnerId and either EC2SecurityGroupName or EC2SecurityGroupId). 



========
Synopsis
========

::

    revoke-db-security-group-ingress
  --db-security-group-name <value>
  [--cidrip <value>]
  [--ec2-security-group-name <value>]
  [--ec2-security-group-id <value>]
  [--ec2-security-group-owner-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-security-group-name`` (string)


  The name of the DB security group to revoke ingress from. 

  

``--cidrip`` (string)


  The IP range to revoke access from. Must be a valid CIDR range. If ``CIDRIP`` is specified, ``EC2SecurityGroupName`` , ``EC2SecurityGroupId`` and ``EC2SecurityGroupOwnerId`` cannot be provided. 

  

``--ec2-security-group-name`` (string)


  The name of the EC2 security group to revoke access from. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, EC2SecurityGroupOwnerId and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

  

``--ec2-security-group-id`` (string)


  The id of the EC2 security group to revoke access from. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, EC2SecurityGroupOwnerId and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

  

``--ec2-security-group-owner-id`` (string)


  The AWS Account Number of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` parameter. The AWS Access Key ID is not an acceptable value. For VPC DB security groups, ``EC2SecurityGroupId`` must be provided. Otherwise, EC2SecurityGroupOwnerId and either ``EC2SecurityGroupName`` or ``EC2SecurityGroupId`` must be provided. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

        

        

      

    

  

