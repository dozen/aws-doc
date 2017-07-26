[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-option-group-options:


*****************************
describe-option-group-options
*****************************



===========
Description
===========



Describes all available options. 



``describe-option-group-options`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``OptionGroupOptions``


========
Synopsis
========

::

    describe-option-group-options
  --engine-name <value>
  [--major-engine-version <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--engine-name`` (string)


  A required parameter. Options available for the given engine name will be described. 

  

``--major-engine-version`` (string)


  If specified, filters the results to include only options for the specified major engine version. 

  

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

OptionGroupOptions -> (list)

  

  List of available option group options. 

  

  (structure)

    

    Available option. 

    

    Name -> (string)

      

      The name of the option. 

      

      

    Description -> (string)

      

      The description of the option. 

      

      

    EngineName -> (string)

      

      The name of the engine that this option can be applied to. 

      

      

    MajorEngineVersion -> (string)

      

      Indicates the major engine version that the option is available for. 

      

      

    MinimumRequiredMinorEngineVersion -> (string)

      

      The minimum required engine version for the option to be applied. 

      

      

    PortRequired -> (boolean)

      

      Specifies whether the option requires a port. 

      

      

    DefaultPort -> (integer)

      

      If the option requires a port, specifies the default port for the option. 

      

      

    OptionsDependedOn -> (list)

      

      List of all options that are prerequisites for this option. 

      

      (string)

        

        

      

    Persistent -> (boolean)

      

      A persistent option cannot be removed from the option group once the option group is used, but this option can be removed from the db instance while modifying the related data and assigning another option group without this option. 

      

      

    Permanent -> (boolean)

      

      A permanent option cannot be removed from the option group once the option group is used, and it cannot be removed from the db instance after assigning an option group with this permanent option. 

      

      

    OptionGroupOptionSettings -> (list)

      

      Specifies the option settings that are available (and the default value) for each option in an option group. 

      

      (structure)

        

        Option group option settings are used to display settings available for each option with their default values and other information. These values are used with the describe-option-group-options action. 

        

        SettingName -> (string)

          

          The name of the option group option. 

          

          

        SettingDescription -> (string)

          

          The description of the option group option. 

          

          

        DefaultValue -> (string)

          

          The default value for the option group option. 

          

          

        ApplyType -> (string)

          

          The DB engine specific parameter type for the option group option. 

          

          

        AllowedValues -> (string)

          

          Indicates the acceptable values for the option group option. 

          

          

        IsModifiable -> (boolean)

          

          Boolean value where true indicates that this option group option can be changed from the default value. 

          

          

        

      

    

  

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` .

  

  

