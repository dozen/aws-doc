[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-cluster-parameters:


***************************
describe-cluster-parameters
***************************



===========
Description
===========



Returns a detailed list of parameters contained within the specified Amazon Redshift parameter group. For each parameter the response includes information such as parameter name, description, data type, value, whether the parameter value is modifiable, and so on. 

 

You can specify *source* filter to retrieve parameters of only specific type. For example, to retrieve parameters that were modified by a user action such as from  modify-cluster-parameter-group , you can specify *source* equal to *user* .

 

For more information about parameters and parameter groups, go to `Amazon Redshift Parameter Groups`_ in the *Amazon Redshift Cluster Management Guide* . 



``describe-cluster-parameters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Parameters``


========
Synopsis
========

::

    describe-cluster-parameters
  --parameter-group-name <value>
  [--source <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--parameter-group-name`` (string)


  The name of a cluster parameter group for which to return details. 

  

``--source`` (string)


  The parameter types to return. Specify ``user`` to show parameters that are different form the default. Similarly, specify ``engine-default`` to show parameters that are the same as the default parameter group. 

   

  Default: All parameter types returned.

   

  Valid Values: ``user`` | ``engine-default`` 

  

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



========
Examples
========

Retrieve the Parameters for a Specified Cluster Parameter Group
---------------------------------------------------------------

This example retrieves the parameters for the named parameter group.  By default, the output is in JSON format.

Command::

   aws redshift describe-cluster-parameters --parameter-group-name myclusterparametergroup

Result::

    {
       "Parameters": [
          {
             "Description": "Sets the display format for date and time values.",
             "DataType": "string",
             "IsModifiable": true,
             "Source": "engine-default",
             "ParameterValue": "ISO, MDY",
             "ParameterName": "datestyle"
          },
          {
             "Description": "Sets the number of digits displayed for floating-point values",
             "DataType": "integer",
             "IsModifiable": true,
             "AllowedValues": "-15-2",
             "Source": "engine-default",
             "ParameterValue": "0",
             "ParameterName": "extra_float_digits"
          },
          (...remaining output omitted...)
       ]
    }

You can also obtain the same information in text format using the ``--output text`` option.

Command::

   aws redshift describe-cluster-parameters --parameter-group-name myclusterparametergroup --output text

Result::

    RESPONSEMETADATA	cdac40aa-64cc-11e2-9e70-918437dd236d
    Sets the display format for date and time values.	string	True	engine-default	ISO, MDY	datestyle
    Sets the number of digits displayed for floating-point values	integer	True	-15-2	engine-default	0	extra_float_digits
    This parameter applies a user-defined label to a group of queries that are run during the same session..	string	True	engine-default	default	query_group
    require ssl for all databaseconnections	boolean	True	true,false	engine-default	false	require_ssl
    Sets the schema search order for names that are not schema-qualified.	string	True	engine-default	$user, public	search_path
    Aborts any statement that takes over the specified number of milliseconds.	integer	True	engine-default	0	statement_timeout
    wlm json configuration	string	True	engine-default	\[{"query_concurrency":5}]	wlm_json_configuration




======
Output
======

Parameters -> (list)

  

  A list of  Parameter instances. Each instance lists the parameters of one cluster parameter group. 

  

  (structure)

    

    Describes a parameter in a cluster parameter group. 

    

    ParameterName -> (string)

      

      The name of the parameter. 

      

      

    ParameterValue -> (string)

      

      The value of the parameter. 

      

      

    Description -> (string)

      

      A description of the parameter. 

      

      

    Source -> (string)

      

      The source of the parameter value, such as "engine-default" or "user". 

      

      

    DataType -> (string)

      

      The data type of the parameter. 

      

      

    AllowedValues -> (string)

      

      The valid range of values for the parameter. 

      

      

    ApplyType -> (string)

      

      Specifies how to apply the parameter. Supported value: ``static`` .

      

      

    IsModifiable -> (boolean)

      

      If ``true`` , the parameter can be modified. Some parameters have security or operational implications that prevent them from being changed. 

      

      

    MinimumEngineVersion -> (string)

      

      The earliest engine version to which the parameter can apply. 

      

      

    

  

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  



.. _Amazon Redshift Parameter Groups: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-parameter-groups.html
