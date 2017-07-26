[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds copy-option-group:


*****************
copy-option-group
*****************



===========
Description
===========



Copies the specified option group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/CopyOptionGroup>`_


========
Synopsis
========

::

    copy-option-group
  --source-option-group-identifier <value>
  --target-option-group-identifier <value>
  --target-option-group-description <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-option-group-identifier`` (string)


  The identifier or ARN for the source option group. For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN) <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.ARN.html#USER_Tagging.ARN.Constructing>`_ . 

   

  Constraints:

   

   
  * Must specify a valid option group. 
   
  * If the source option group is in the same region as the copy, specify a valid option group identifier, for example ``my-option-group`` , or a valid ARN. 
   
  * If the source option group is in a different region than the copy, specify a valid option group ARN, for example ``arn:aws:rds:us-west-2:123456789012:og:special-options`` . 
   

  

``--target-option-group-identifier`` (string)


  The identifier for the copied option group.

   

  Constraints:

   

   
  * Cannot be null, empty, or blank 
   
  * Must contain from 1 to 255 alphanumeric characters or hyphens 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

   

  Example: ``my-option-group``  

  

``--target-option-group-description`` (string)


  The description for the copied option group.

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

        

        

      OptionVersion -> (string)

        

        The version of the option.

        

        

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

    

    

  OptionGroupArn -> (string)

    

    The Amazon Resource Name (ARN) for the option group.

    

    

  

