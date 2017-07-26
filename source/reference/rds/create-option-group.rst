[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds create-option-group:


*******************
create-option-group
*******************



===========
Description
===========



Creates a new option group. You can create up to 20 option groups. 



========
Synopsis
========

::

    create-option-group
  --option-group-name <value>
  --engine-name <value>
  --major-engine-version <value>
  --option-group-description <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--option-group-name`` (string)


  Specifies the name of the option group to be created. 

   

  Constraints: 

   

   
  * Must be 1 to 255 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

   

  Example: ``myoptiongroup`` 

  

``--engine-name`` (string)


  Specifies the name of the engine that this option group should be associated with. 

  

``--major-engine-version`` (string)


  Specifies the major version of the engine that this option group should be associated with. 

  

``--option-group-description`` (string)


  The description of the option group. 

  

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

**To Create an Amazon RDS option group**

The following ``create-option-group`` command creates a new Amazon RDS option group::

   aws rds create-option-group --option-group-name MyOptionGroup --engine-name oracle-ee --major-engine-version 11.2 --option-group-description "Oracle Database Manager Database Control" 

In the example, the option group is created for Oracle Enterprise Edition version *11.2*, is named *MyOptionGroup* and
includes a description.

This command output a JSON block that contains information on the option group.

For more information, see `Create an Amazon RDS Option Group`_ in the *AWS Command Line Interface User Guide*.

.. _`Create an Amazon RDS Option Group`: http://docs.aws.amazon.com/cli/latest/userguide/cli-rds-create-option-group.html



======
Output
======

OptionGroup -> (structure)

  

  

  

  OptionGroupName -> (string)

    

    Specifies the name of the option group. 

    

    

  OptionGroupDescription -> (string)

    

    Provides a description of the option group. 

    

    

  EngineName -> (string)

    

    Indicates the name of the engine that this option group can be applied to. 

    

    

  MajorEngineVersion -> (string)

    

    Indicates the major engine version associated with this option group. 

    

    

  Options -> (list)

    

    Indicates what options are available in the option group. 

    

    (structure)

      

      Option details. 

      

      OptionName -> (string)

        

        The name of the option. 

        

        

      OptionDescription -> (string)

        

        The description of the option. 

        

        

      Persistent -> (boolean)

        

        Indicate if this option is persistent. 

        

        

      Permanent -> (boolean)

        

        Indicate if this option is permanent.

        

        

      Port -> (integer)

        

        If required, the port configured for this option to use. 

        

        

      OptionSettings -> (list)

        

        The option settings for this option. 

        

        (structure)

          

          Option settings are the actual settings being applied or configured for that option. It is used when you modify an option group or describe option groups. For example, the NATIVE_NETWORK_ENCRYPTION option has a setting called SQLNET.ENCRYPTION_SERVER that can have several different values. 

          

          Name -> (string)

            

            The name of the option that has settings that you can set. 

            

            

          Value -> (string)

            

            The current value of the option setting. 

            

            

          DefaultValue -> (string)

            

            The default value of the option setting. 

            

            

          Description -> (string)

            

            The description of the option setting. 

            

            

          ApplyType -> (string)

            

            The DB engine specific parameter type. 

            

            

          DataType -> (string)

            

            The data type of the option setting. 

            

            

          AllowedValues -> (string)

            

            The allowed values of the option setting. 

            

            

          IsModifiable -> (boolean)

            

            A Boolean value that, when true, indicates the option setting can be modified from the default. 

            

            

          IsCollection -> (boolean)

            

            Indicates if the option setting is part of a collection. 

            

            

          

        

      DBSecurityGroupMemberships -> (list)

        

        If the option requires access to a port, then this DB security group allows access to the port. 

        

        (structure)

          

          This data type is used as a response element in the following actions: 

           

           
          *  modify-db-instance  
           
          *  reboot-db-instance  
           
          *  restore-db-instance-from-db-snapshot  
           
          *  restore-db-instance-to-point-in-time  
           

          

          DBSecurityGroupName -> (string)

            

            The name of the DB security group. 

            

            

          Status -> (string)

            

            The status of the DB security group. 

            

            

          

        

      VpcSecurityGroupMemberships -> (list)

        

        If the option requires access to a port, then this VPC security group allows access to the port. 

        

        (structure)

          

          This data type is used as a response element for queries on VPC security group membership.

          

          VpcSecurityGroupId -> (string)

            

            The name of the VPC security group.

            

            

          Status -> (string)

            

            The status of the VPC security group. 

            

            

          

        

      

    

  AllowsVpcAndNonVpcInstanceMemberships -> (boolean)

    

    Indicates whether this option group can be applied to both VPC and non-VPC instances. The value ``true`` indicates the option group can be applied to both VPC and non-VPC instances. 

    

    

  VpcId -> (string)

    

    If **AllowsVpcAndNonVpcInstanceMemberships** is ``false`` , this field is blank. If **AllowsVpcAndNonVpcInstanceMemberships** is ``true`` and this field is blank, then this option group can be applied to both VPC and non-VPC instances. If this field contains a value, then this option group can only be applied to instances that are in the VPC indicated by this field. 

    

    

  

