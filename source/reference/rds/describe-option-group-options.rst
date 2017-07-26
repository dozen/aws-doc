[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-option-group-options:


*****************************
describe-option-group-options
*****************************



===========
Description
===========



Describes all available options.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeOptionGroupOptions>`_


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
  [--generate-cli-skeleton <value>]




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

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      The options that are prerequisites for this option.

      

      (string)

        

        

      

    OptionsConflictsWith -> (list)

      

      The options that conflict with this option.

      

      (string)

        

        

      

    Persistent -> (boolean)

      

      Persistent options can't be removed from an option group while DB instances are associated with the option group. If you disassociate all DB instances from the option group, your can remove the persistent option from the option group.

      

      

    Permanent -> (boolean)

      

      Permanent options can never be removed from an option group. An option group containing a permanent option can't be removed from a DB instance.

      

      

    OptionGroupOptionSettings -> (list)

      

      The option settings that are available (and the default value) for each option in an option group.

      

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

          

          

        

      

    OptionGroupOptionVersions -> (list)

      

      The versions that are available for the option.

      

      (structure)

        

        The version for an option. Option group option versions are returned by the  describe-option-group-options action.

        

        Version -> (string)

          

          The version of the option.

          

          

        IsDefault -> (boolean)

          

          True if the version is the default version of the option; otherwise, false.

          

          

        

      

    

  

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` .

  

  

