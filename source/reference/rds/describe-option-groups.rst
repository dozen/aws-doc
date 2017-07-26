[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-option-groups:


**********************
describe-option-groups
**********************



===========
Description
===========



Describes the available option groups. 



``describe-option-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``OptionGroupsList``


========
Synopsis
========

::

    describe-option-groups
  [--option-group-name <value>]
  [--filters <value>]
  [--engine-name <value>]
  [--major-engine-version <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--option-group-name`` (string)


  The name of the option group to describe. Cannot be supplied together with EngineName or MajorEngineVersion. 

  

``--filters`` (list)


  This parameter is not currently supported.

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--engine-name`` (string)


  Filters the list of option groups to only include groups associated with a specific database engine. 

  

``--major-engine-version`` (string)


  Filters the list of option groups to only include groups associated with a specific database engine version. If specified, then EngineName must also be specified. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

OptionGroupsList -> (list)

  

  List of option groups. 

  

  (structure)

    

    

    

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

      

      

    

  

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

