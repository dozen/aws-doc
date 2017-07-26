[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam simulate-custom-policy:


**********************
simulate-custom-policy
**********************



===========
Description
===========



Simulate how a set of IAM policies and optionally a resource-based policy works with a list of API actions and AWS resources to determine the policies' effective permissions. The policies are provided as strings.

 

The simulation does not perform the API actions; it only checks the authorization to determine if the simulated policies allow or deny the actions.

 

If you want to simulate existing policies attached to an IAM user, group, or role, use  simulate-principal-policy instead.

 

Context keys are variables maintained by AWS and its services that provide details about the context of an API query request. You can use the ``Condition`` element of an IAM policy to evaluate context keys. To get the list of context keys that the policies require for correct simulation, use  get-context-keys-for-custom-policy .

 

If the output is long, you can use ``MaxItems`` and ``Marker`` parameters to paginate the results.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/SimulateCustomPolicy>`_


``simulate-custom-policy`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``EvaluationResults``


========
Synopsis
========

::

    simulate-custom-policy
  --policy-input-list <value>
  --action-names <value>
  [--resource-arns <value>]
  [--resource-policy <value>]
  [--resource-owner <value>]
  [--caller-arn <value>]
  [--context-entries <value>]
  [--resource-handling-option <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-input-list`` (list)


  A list of policy documents to include in the simulation. Each document is specified as a string containing the complete, valid JSON text of an IAM policy. Do not include any resource-based policies in this parameter. Any resource-based policy must be submitted with the ``ResourcePolicy`` parameter. The policies cannot be "scope-down" policies, such as you could include in a call to `GetFederationToken <http://docs.aws.amazon.com/IAM/latest/APIReference/API_GetFederationToken.html>`_ or one of the `AssumeRole <http://docs.aws.amazon.com/IAM/latest/APIReference/API_AssumeRole.html>`_ APIs to restrict what a user can do while using the temporary credentials.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ used to validate this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range as well as the printable characters in the Basic Latin and Latin-1 Supplement character set (through \u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

  



Syntax::

  "string" "string" ...



``--action-names`` (list)


  A list of names of API actions to evaluate in the simulation. Each action is evaluated against each resource. Each action must include the service identifier, such as ``iam:CreateUser`` .

  



Syntax::

  "string" "string" ...



``--resource-arns`` (list)


  A list of ARNs of AWS resources to include in the simulation. If this parameter is not provided then the value defaults to ``*`` (all resources). Each API in the ``ActionNames`` parameter is evaluated for each resource in this list. The simulation determines the access result (allowed or denied) of each combination and reports it in the response.

   

  The simulation does not automatically retrieve policies for the specified resources. If you want to include a resource policy in the simulation, then you must include the policy as a string in the ``ResourcePolicy`` parameter.

   

  If you include a ``ResourcePolicy`` , then it must be applicable to all of the resources included in the simulation or you receive an invalid input error.

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* .

  



Syntax::

  "string" "string" ...



``--resource-policy`` (string)


  A resource-based policy to include in the simulation provided as a string. Each resource in the simulation is treated as if it had this policy attached. You can include only one resource-based policy in a simulation.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ used to validate this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range as well as the printable characters in the Basic Latin and Latin-1 Supplement character set (through \u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

  

``--resource-owner`` (string)


  An AWS account ID that specifies the owner of any simulated resource that does not identify its owner in the resource ARN, such as an S3 bucket or object. If ``ResourceOwner`` is specified, it is also used as the account owner of any ``ResourcePolicy`` included in the simulation. If the ``ResourceOwner`` parameter is not specified, then the owner of the resources and the resource policy defaults to the account of the identity provided in ``CallerArn`` . This parameter is required only if you specify a resource-based policy and account that owns the resource is different from the account that owns the simulated calling user ``CallerArn`` .

  

``--caller-arn`` (string)


  The ARN of the IAM user that you want to use as the simulated caller of the APIs. ``CallerArn`` is required if you include a ``ResourcePolicy`` so that the policy's ``Principal`` element has a value to use in evaluating the policy.

   

  You can specify only the ARN of an IAM user. You cannot specify the ARN of an assumed role, federated user, or a service principal.

  

``--context-entries`` (list)


  A list of context keys and corresponding values for the simulation to use. Whenever a context key is evaluated in one of the simulated IAM permission policies, the corresponding value is supplied.

  



Shorthand Syntax::

    ContextKeyName=string,ContextKeyValues=string,string,ContextKeyType=string ...




JSON Syntax::

  [
    {
      "ContextKeyName": "string",
      "ContextKeyValues": ["string", ...],
      "ContextKeyType": "string"|"stringList"|"numeric"|"numericList"|"boolean"|"booleanList"|"ip"|"ipList"|"binary"|"binaryList"|"date"|"dateList"
    }
    ...
  ]



``--resource-handling-option`` (string)


  Specifies the type of simulation to run. Different APIs that support resource-based policies require different combinations of resources. By specifying the type of simulation to run, you enable the policy simulator to enforce the presence of the required resources to ensure reliable simulation results. If your simulation does not match one of the following scenarios, then you can omit this parameter. The following list shows each of the supported scenario values and the resources that you must define to run the simulation.

   

  Each of the EC2 scenarios requires that you specify instance, image, and security-group resources. If your scenario includes an EBS volume, then you must specify that volume as a resource. If the EC2 scenario includes VPC, then you must supply the network-interface resource. If it includes an IP subnet, then you must specify the subnet resource. For more information on the EC2 scenario options, see `Supported Platforms <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-supported-platforms.html>`_ in the *AWS EC2 User Guide* .

   

   
  * **EC2-Classic-InstanceStore**   instance, image, security-group 
   
  * **EC2-Classic-EBS**   instance, image, security-group, volume 
   
  * **EC2-VPC-InstanceStore**   instance, image, security-group, network-interface 
   
  * **EC2-VPC-InstanceStore-Subnet**   instance, image, security-group, network-interface, subnet 
   
  * **EC2-VPC-EBS**   instance, image, security-group, network-interface, volume 
   
  * **EC2-VPC-EBS-Subnet**   instance, image, security-group, network-interface, subnet, volume 
   

  

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EvaluationResults -> (list)

  

  The results of the simulation.

  

  (structure)

    

    Contains the results of a simulation.

     

    This data type is used by the return parameter of ``  simulate-custom-policy `` and ``  simulate-principal-policy `` .

    

    EvalActionName -> (string)

      

      The name of the API action tested on the indicated resource.

      

      

    EvalResourceName -> (string)

      

      The ARN of the resource that the indicated API action was tested on.

      

      

    EvalDecision -> (string)

      

      The result of the simulation.

      

      

    MatchedStatements -> (list)

      

      A list of the statements in the input policies that determine the result for this scenario. Remember that even if multiple statements allow the action on the resource, if only one statement denies that action, then the explicit deny overrides any allow, and the deny statement is the only entry included in the result.

      

      (structure)

        

        Contains a reference to a ``Statement`` element in a policy document that determines the result of the simulation.

         

        This data type is used by the ``MatchedStatements`` member of the ``  EvaluationResult `` type.

        

        SourcePolicyId -> (string)

          

          The identifier of the policy that was provided as an input.

          

          

        SourcePolicyType -> (string)

          

          The type of the policy.

          

          

        StartPosition -> (structure)

          

          The row and column of the beginning of the ``Statement`` in an IAM policy.

          

          Line -> (integer)

            

            The line containing the specified position in the document.

            

            

          Column -> (integer)

            

            The column in the line containing the specified position in the document.

            

            

          

        EndPosition -> (structure)

          

          The row and column of the end of a ``Statement`` in an IAM policy.

          

          Line -> (integer)

            

            The line containing the specified position in the document.

            

            

          Column -> (integer)

            

            The column in the line containing the specified position in the document.

            

            

          

        

      

    MissingContextValues -> (list)

      

      A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. This list is used when the resource in a simulation is "*", either explicitly, or when the ``ResourceArns`` parameter blank. If you include a list of resources, then any missing context values are instead included under the ``ResourceSpecificResults`` section. To discover the context keys used by a set of policies, you can call  get-context-keys-for-custom-policy or  get-context-keys-for-principal-policy .

      

      (string)

        

        

      

    OrganizationsDecisionDetail -> (structure)

      

      A structure that details how AWS Organizations and its service control policies affect the results of the simulation. Only applies if the simulated user's account is part of an organization.

      

      AllowedByOrganizations -> (boolean)

        

        Specifies whether the simulated action is allowed by the AWS Organizations service control policies that impact the simulated user's account.

        

        

      

    EvalDecisionDetails -> (map)

      

      Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access. See `How IAM Roles Differ from Resource-based Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_compare-resource-policies.html>`_  

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    ResourceSpecificResults -> (list)

      

      The individual results of the simulation of the API action specified in EvalActionName on each resource.

      

      (structure)

        

        Contains the result of the simulation of a single API action call on a single resource.

         

        This data type is used by a member of the  EvaluationResult data type.

        

        EvalResourceName -> (string)

          

          The name of the simulated resource, in Amazon Resource Name (ARN) format.

          

          

        EvalResourceDecision -> (string)

          

          The result of the simulation of the simulated API action on the resource specified in ``EvalResourceName`` .

          

          

        MatchedStatements -> (list)

          

          A list of the statements in the input policies that determine the result for this part of the simulation. Remember that even if multiple statements allow the action on the resource, if *any* statement denies that action, then the explicit deny overrides any allow, and the deny statement is the only entry included in the result.

          

          (structure)

            

            Contains a reference to a ``Statement`` element in a policy document that determines the result of the simulation.

             

            This data type is used by the ``MatchedStatements`` member of the ``  EvaluationResult `` type.

            

            SourcePolicyId -> (string)

              

              The identifier of the policy that was provided as an input.

              

              

            SourcePolicyType -> (string)

              

              The type of the policy.

              

              

            StartPosition -> (structure)

              

              The row and column of the beginning of the ``Statement`` in an IAM policy.

              

              Line -> (integer)

                

                The line containing the specified position in the document.

                

                

              Column -> (integer)

                

                The column in the line containing the specified position in the document.

                

                

              

            EndPosition -> (structure)

              

              The row and column of the end of a ``Statement`` in an IAM policy.

              

              Line -> (integer)

                

                The line containing the specified position in the document.

                

                

              Column -> (integer)

                

                The column in the line containing the specified position in the document.

                

                

              

            

          

        MissingContextValues -> (list)

          

          A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. This list is used when a list of ARNs is included in the ``ResourceArns`` parameter instead of "*". If you do not specify individual resources, by setting ``ResourceArns`` to "*" or by not including the ``ResourceArns`` parameter, then any missing context values are instead included under the ``EvaluationResults`` section. To discover the context keys used by a set of policies, you can call  get-context-keys-for-custom-policy or  get-context-keys-for-principal-policy .

          

          (string)

            

            

          

        EvalDecisionDetails -> (map)

          

          Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access.

          

          key -> (string)

            

            

          value -> (string)

            

            

          

        

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  

