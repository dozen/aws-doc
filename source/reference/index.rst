

.. _cli:aws:


***
aws
***



===========
Description
===========

The AWS Command Line Interface is a unified tool to manage your AWS services.



========
Synopsis
========

::

    aws [options] <command> <subcommand> [parameters]


Use *aws command help* for information on a specific command. Use *aws help topics* to view a list of available help topics. The synopsis for each command shows its parameters and their usage. Optional parameters are shown in square brackets.



=======
Options
=======

``--debug`` (boolean)


Turn on debug logging.

``--endpoint-url`` (string)


Override command's default URL with the given URL.

``--no-verify-ssl`` (boolean)


By default, the AWS CLI uses SSL when communicating with AWS services. For each SSL connection, the AWS CLI will verify SSL certificates. This option overrides the default behavior of verifying SSL certificates.

``--no-paginate`` (boolean)


Disable automatic pagination.

``--output`` (string)


The formatting style for command output.




* json


* text


* table



``--query`` (string)


A JMESPath query to use in filtering the response data.

``--profile`` (string)


Use a specific profile from your credential file.

``--region`` (string)


The region to use. Overrides config/env settings.

``--version`` (string)


Display the version of this tool.

``--color`` (string)


Turn on/off color output.




* on


* off


* auto



``--no-sign-request`` (boolean)


Do not sign requests. Credentials will not be loaded if this argument is provided.

``--ca-bundle`` (string)


The CA certificate bundle to use when verifying SSL certificates. Overrides config/env settings.

``--cli-read-timeout`` (int)


The maximum socket read time in seconds. If the value is set to 0, the socket read will be blocking and not timeout.

``--cli-connect-timeout`` (int)


The maximum socket connect time in seconds. If the value is set to 0, the socket connect will be blocking and not timeout.



==================
Available Services
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  acm/index
  apigateway/index
  application-autoscaling/index
  appstream/index
  athena/index
  autoscaling/index
  batch/index
  budgets/index
  clouddirectory/index
  cloudformation/index
  cloudfront/index
  cloudhsm/index
  cloudsearch/index
  cloudsearchdomain/index
  cloudtrail/index
  cloudwatch/index
  codebuild/index
  codecommit/index
  codepipeline/index
  codestar/index
  cognito-identity/index
  cognito-idp/index
  cognito-sync/index
  configservice/index
  configure/index
  cur/index
  datapipeline/index
  dax/index
  deploy/index
  devicefarm/index
  directconnect/index
  discovery/index
  dms/index
  ds/index
  dynamodb/index
  dynamodbstreams/index
  ec2/index
  ecr/index
  ecs/index
  efs/index
  elasticache/index
  elasticbeanstalk/index
  elastictranscoder/index
  elb/index
  elbv2/index
  emr/index
  es/index
  events/index
  firehose/index
  gamelift/index
  glacier/index
  greengrass/index
  health/index
  iam/index
  importexport/index
  inspector/index
  iot/index
  iot-data/index
  kinesis/index
  kinesisanalytics/index
  kms/index
  lambda/index
  lex-models/index
  lex-runtime/index
  lightsail/index
  logs/index
  machinelearning/index
  marketplace-entitlement/index
  marketplacecommerceanalytics/index
  meteringmarketplace/index
  mturk/index
  opsworks/index
  opsworks-cm/index
  organizations/index
  pinpoint/index
  polly/index
  rds/index
  redshift/index
  rekognition/index
  resourcegroupstaggingapi/index
  route53/index
  route53domains/index
  s3/index
  s3api/index
  sdb/index
  servicecatalog/index
  ses/index
  shield/index
  sms/index
  snowball/index
  sns/index
  sqs/index
  ssm/index
  stepfunctions/index
  storagegateway/index
  sts/index
  support/index
  swf/index
  waf/index
  waf-regional/index
  workdocs/index
  workspaces/index
  xray/index


========
See Also
========

* :ref:`aws help topics <cli:aws help topics>`
