[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift modify-cluster-parameter-group:


******************************
modify-cluster-parameter-group
******************************



===========
Description
===========



Modifies the parameters of a parameter group.

 

For more information about parameters and parameter groups, go to `Amazon Redshift Parameter Groups <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-parameter-groups.html>`_ in the *Amazon Redshift Cluster Management Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/ModifyClusterParameterGroup>`_


========
Synopsis
========

::

    modify-cluster-parameter-group
  --parameter-group-name <value>
  --parameters <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--parameter-group-name`` (string)


  The name of the parameter group to be modified.

  

``--parameters`` (list)


  An array of parameters to be modified. A maximum of 20 parameters can be modified in a single request.

   

  For each parameter to be modified, you must supply at least the parameter name and parameter value; other name-value pairs of the parameter are optional.

   

  For the workload management (WLM) configuration, you must supply all the name-value pairs in the wlm_json_configuration parameter.

  



Shorthand Syntax::

    ParameterName=string,ParameterValue=string,Description=string,Source=string,DataType=string,AllowedValues=string,ApplyType=string,IsModifiable=boolean,MinimumEngineVersion=string ...




JSON Syntax::

  [
    {
      "ParameterName": "string",
      "ParameterValue": "string",
      "Description": "string",
      "Source": "string",
      "DataType": "string",
      "AllowedValues": "string",
      "ApplyType": "static"|"dynamic",
      "IsModifiable": true|false,
      "MinimumEngineVersion": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

Modify a Parameter in a Parameter Group
---------------------------------------

This example shows how to modify the *wlm_json_configuration* parameter for workload management.

Command::

   aws redshift modify-cluster-parameter-group --parameter-group-name myclusterparametergroup --parameters '{"parameter_name":"wlm_json_configuration","parameter_value":"\[{\\"user_group\\":\[\\"example_user_group1\\"],\\"query_group\\":\[\\"example_query_group1\\"],\\"query_concurrency\\":7},{\\"query_concurrency\\":5}]"}'

Result::

    {
       "ParameterGroupStatus": "Your parameter group has been updated but changes won't get applied until you reboot the associated Clusters.",
       "ParameterGroupName": "myclusterparametergroup",
       "ResponseMetadata": {
          "RequestId": "09974cc0-64cd-11e2-bea9-49e0ce183f07"
       }
    }



======
Output
======

ParameterGroupName -> (string)

  

  The name of the cluster parameter group.

  

  

ParameterGroupStatus -> (string)

  

  The status of the parameter group. For example, if you made a change to a parameter group name-value pair, then the change could be pending a reboot of an associated cluster.

  

  

