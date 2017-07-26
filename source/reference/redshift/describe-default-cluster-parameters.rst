[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-default-cluster-parameters:


***********************************
describe-default-cluster-parameters
***********************************



===========
Description
===========



Returns a list of parameter settings for the specified parameter group family. 

 

For more information about parameters and parameter groups, go to `Amazon Redshift Parameter Groups`_ in the *Amazon Redshift Cluster Management Guide* . 



``describe-default-cluster-parameters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DefaultClusterParameters.Parameters``


========
Synopsis
========

::

    describe-default-cluster-parameters
  --parameter-group-family <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--parameter-group-family`` (string)


  The name of the cluster parameter group family. 

  

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

Get a Description of Default Cluster Parameters
-----------------------------------------------

This example returns a description of the default cluster parameters for the
``redshift-1.0`` family. By default, the output is in JSON format.

Command::

   aws redshift describe-default-cluster-parameters --parameter-group-family redshift-1.0

Result::

    {
       "DefaultClusterParameters": {
       "ParameterGroupFamily": "redshift-1.0",
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
    }

.. tip:: To see a list of valid parameter group families, use the ``describe-cluster-parameter-groups`` command.



======
Output
======

DefaultClusterParameters -> (structure)

  

  Describes the default cluster parameters for a parameter group family. 

  

  ParameterGroupFamily -> (string)

    

    The name of the cluster parameter group family to which the engine default parameters apply. 

    

    

  Marker -> (string)

    

    A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

    

    

  Parameters -> (list)

    

    The list of cluster default parameters. 

    

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

        

        

      

    

  



.. _Amazon Redshift Parameter Groups: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-parameter-groups.html
