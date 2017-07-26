[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation deploy:


******
deploy
******



===========
Description
===========

Deploys the specified AWS CloudFormation template by creating and then executing
a change set. The command terminates after AWS CloudFormation executes the
change set. If you want to view the change set before AWS CloudFormation
executes it, use the ``--no-execute-changeset`` flag.

To update a stack, specify the name of an existing stack. To create a new stack,
specify a new stack name.





========
Synopsis
========

::

    deploy
  --template-file <value>
  --stack-name <value>
  [--parameter-overrides <value> [<value>...]]
  [--capabilities <value> [<value>...]]
  [--no-execute-changeset]




=======
Options
=======

``--template-file`` (string)
The path where your AWS CloudFormation template is located.

``--stack-name`` (string)
The name of the AWS CloudFormation stack you're deploying to. If you specify an existing stack, the command updates the stack. If you specify a new stack, the command creates it.

``--parameter-overrides`` (list)
A list of parameter structures that specify input parameters for your stack template. If you're updating a stack and you don't specify a parameter, the command uses the stack's existing value. For new stacks, you must specify parameters that don't have a default value. Syntax: ParameterKey1=ParameterValue1 ParameterKey2=ParameterValue2 ...



Syntax::

  "string" "string" ...



``--capabilities`` (list)
A list of capabilities that you must specify before AWS Cloudformation can create certain stacks. Some stack templates might include resources that can affect permissions in your AWS account, for example, by creating new AWS Identity and Access Management (IAM) users. For those stacks, you must explicitly acknowledge their capabilities by specifying this parameter. The only valid values are CAPABILITY_IAM and CAPABILITY_NAMED_IAM. If you have IAM resources, you can specify either capability. If you have IAM resources with custom names, you must specify CAPABILITY_NAMED_IAM. If you don't specify this parameter, this action returns an InsufficientCapabilities error.



Syntax::

  "string" "string" ...

  Where valid values are:
    CAPABILITY_IAM
    CAPABILITY_NAMED_IAM





``--no-execute-changeset`` (boolean)
Indicates whether to execute the change set. Specify this flag if you want to view your stack changes before executing the change set. The command creates an AWS CloudFormation change set and then exits without executing the change set. After you view the change set, execute it to implement your changes.



========
Examples
========

Following command deploys template named ``template.json`` to a stack named
``my-new-stack``::


    aws cloudformation deploy --template-file /path_to_template/template.json --stack-name my-new-stack --parameter-overrides Key1=Value1 Key2=Value2

