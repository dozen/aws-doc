[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds add-option-to-option-group:


**************************
add-option-to-option-group
**************************



===========
Description
===========



Modifies an existing option group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/ModifyOptionGroup>`_


========
Synopsis
========

::

    add-option-to-option-group
  --option-group-name <value>
  [--apply-immediately | --no-apply-immediately]
  [--options <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--option-group-name`` (string)


  The name of the option group to be modified.

   

  Permanent options, such as the TDE option for Oracle Advanced Security TDE, cannot be removed from an option group, and that option group cannot be removed from a DB instance once it is associated with a DB instance

  

``--apply-immediately`` | ``--no-apply-immediately`` (boolean)


  Indicates whether the changes should be applied immediately, or during the next maintenance window for each instance associated with the option group.

  

``--options`` (list)


  Options in this list are added to the option group or, if already present, the specified configuration is used to update the existing configuration.

  



Shorthand Syntax::

    OptionName=string,Port=integer,OptionVersion=string,DBSecurityGroupMemberships=string,string,VpcSecurityGroupMemberships=string,string,OptionSettings=[{Name=string,Value=string,DefaultValue=string,Description=string,ApplyType=string,DataType=string,AllowedValues=string,IsModifiable=boolean,IsCollection=boolean},{Name=string,Value=string,DefaultValue=string,Description=string,ApplyType=string,DataType=string,AllowedValues=string,IsModifiable=boolean,IsCollection=boolean}] ...




JSON Syntax::

  [
    {
      "OptionName": "string",
      "Port": integer,
      "OptionVersion": "string",
      "DBSecurityGroupMemberships": ["string", ...],
      "VpcSecurityGroupMemberships": ["string", ...],
      "OptionSettings": [
        {
          "Name": "string",
          "Value": "string",
          "DefaultValue": "string",
          "Description": "string",
          "ApplyType": "string",
          "DataType": "string",
          "AllowedValues": "string",
          "IsModifiable": true|false,
          "IsCollection": true|false
        }
        ...
      ]
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

            

            A apply-immediately value that, when true, indicates the option setting can be modified from the default.

            

            

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

    

    

  

