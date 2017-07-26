[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds create-db-security-group:


************************
create-db-security-group
************************



===========
Description
===========



Creates a new DB security group. DB security groups control access to a DB instance. 



========
Synopsis
========

::

    create-db-security-group
  --db-security-group-name <value>
  --db-security-group-description <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-security-group-name`` (string)


  The name for the DB security group. This value is stored as a lowercase string. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   
  * Must not be "Default"
   
  * Cannot contain spaces
   

   

  Example: ``mysecuritygroup`` 

  

``--db-security-group-description`` (string)


  The description for the DB security group. 

  

``--tags`` (list)


  A list of tags.

  



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

**To create an Amazon RDS DB security group**

The following ``create-db-security-group`` command creates a new Amazon RDS DB security group::

    aws rds create-db-security-group --db-security-group-name mysecgroup --db-security-group-description "My Test Security Group"

In the example, the new DB security group is named ``mysecgroup`` and has a description.

This command output a JSON block that contains information about the DB security group.

For more information, see `Create an Amazon RDS DB Security Group`_ in the *AWS Command Line Interface User Guide*.

.. _`Create an Amazon RDS DB Security Group`: http://docs.aws.amazon.com/cli/latest/userguide/cli-rds-create-secgroup.html



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

        

        

      

    

  

