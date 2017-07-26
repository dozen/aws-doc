[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice put-configuration-recorder:


**************************
put-configuration-recorder
**************************



===========
Description
===========



Creates a new configuration recorder to record the selected resource configurations.

 

You can use this action to change the role ``roleARN`` and/or the ``recordingGroup`` of an existing recorder. To change the role, call the action on the existing configuration recorder and specify a role.

 

.. note::

   

  Currently, you can specify only one configuration recorder per region in your account.

   

  If ``configuration-recorder`` does not have the **recordingGroup** parameter specified, the default is to record all supported resource types.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/PutConfigurationRecorder>`_


========
Synopsis
========

::

    put-configuration-recorder
  --configuration-recorder <value>
  [--recording-group <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-recorder`` (structure)


  The configuration recorder object that records each configuration change made to the resources.

  



Shorthand Syntax::

    name=string,roleARN=string




JSON Syntax::

  {
    "name": "string",
    "roleARN": "string"
  }



``--recording-group`` (structure)


  Specifies the types of AWS resource for which AWS Config records configuration changes.

  



Shorthand Syntax::

    allSupported=boolean,includeGlobalResourceTypes=boolean,resourceTypes=string,string




JSON Syntax::

  {
    "allSupported": true|false,
    "includeGlobalResourceTypes": true|false,
    "resourceTypes": ["AWS::EC2::CustomerGateway"|"AWS::EC2::EIP"|"AWS::EC2::Host"|"AWS::EC2::Instance"|"AWS::EC2::InternetGateway"|"AWS::EC2::NetworkAcl"|"AWS::EC2::NetworkInterface"|"AWS::EC2::RouteTable"|"AWS::EC2::SecurityGroup"|"AWS::EC2::Subnet"|"AWS::CloudTrail::Trail"|"AWS::EC2::Volume"|"AWS::EC2::VPC"|"AWS::EC2::VPNConnection"|"AWS::EC2::VPNGateway"|"AWS::IAM::Group"|"AWS::IAM::Policy"|"AWS::IAM::Role"|"AWS::IAM::User"|"AWS::ACM::Certificate"|"AWS::RDS::DBInstance"|"AWS::RDS::DBSubnetGroup"|"AWS::RDS::DBSecurityGroup"|"AWS::RDS::DBSnapshot"|"AWS::RDS::EventSubscription"|"AWS::ElasticLoadBalancingV2::LoadBalancer"|"AWS::S3::Bucket"|"AWS::SSM::ManagedInstanceInventory"|"AWS::Redshift::Cluster"|"AWS::Redshift::ClusterSnapshot"|"AWS::Redshift::ClusterParameterGroup"|"AWS::Redshift::ClusterSecurityGroup"|"AWS::Redshift::ClusterSubnetGroup"|"AWS::Redshift::EventSubscription"|"AWS::CloudWatch::Alarm", ...]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To record all supported resources**

The following command creates a configuration recorder that tracks changes to all supported resource types, including global resource types::

    aws configservice put-configuration-recorder --configuration-recorder name=default,roleARN=arn:aws:iam::123456789012:role/config-role --recording-group allSupported=true,includeGlobalResourceTypes=true

**To record specific types of resources**

The following command creates a configuration recorder that tracks changes to only those types of resources that are specified in the JSON file for the `--recording-group` option::

    aws configservice put-configuration-recorder --configuration-recorder name=default,roleARN=arn:aws:iam::123456789012:role/config-role --recording-group file://recordingGroup.json

`recordingGroup.json` is a JSON file that specifies the types of resources that AWS Config will record::

    {
      "allSupported": false,
      "includeGlobalResourceTypes": false,
      "resourceTypes": [
        "AWS::EC2::EIP",
        "AWS::EC2::Instance",
        "AWS::EC2::NetworkAcl",
        "AWS::EC2::SecurityGroup",
        "AWS::CloudTrail::Trail",
        "AWS::EC2::Volume",
        "AWS::EC2::VPC",
        "AWS::IAM::User",
        "AWS::IAM::Policy"
      ]
    }

Before you can specify resource types for the `resourceTypes` key, you must set the `allSupported` and `includeGlobalResourceTypes` options to false or omit them.

If the command succeeds, AWS Config returns no output. To verify the settings of your configuration recorder, run the `describe-configuration-recorders`__ command.

.. __: http://docs.aws.amazon.com/cli/latest/reference/configservice/describe-configuration-recorders.html

======
Output
======

None