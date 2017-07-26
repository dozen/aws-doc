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
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-input-list`` (list)


  A list of policy documents to include in the simulation. Each document is specified as a string containing the complete, valid JSON text of an IAM policy. Do not include any resource-based policies in this parameter. Any resource-based policy must be submitted with the ``ResourcePolicy`` parameter. The policies cannot be "scope-down" policies, such as you could include in a call to `GetFederationToken`_ or one of the `AssumeRole`_ APIs to restrict what a user can do while using the temporary credentials.

  



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

  



Syntax::

  "string" "string" ...



``--resource-policy`` (string)


  A resource-based policy to include in the simulation provided as a string. Each resource in the simulation is treated as if it had this policy attached. You can include only one resource-based policy in a simulation.

  

``--resource-owner`` (string)


  An AWS account ID that specifies the owner of any simulated resource that does not identify its owner in the resource ARN, such as an S3 bucket or object. If ``ResourceOwner`` is specified, it is also used as the account owner of any ``ResourcePolicy`` included in the simulation. If the ``ResourceOwner`` parameter is not specified, then the owner of the resources and the resource policy defaults to the account of the identity provided in ``CallerArn`` . This parameter is required only if you specify a resource-based policy and account that owns the resource is different from the account that owns the simulated calling user ``CallerArn`` .

  

``--caller-arn`` (string)


  The ARN of the user that you want to use as the simulated caller of the APIs. ``CallerArn`` is required if you include a ``ResourcePolicy`` so that the policy's ``Principal`` element has a value to use in evaluating the policy.

   

  You can specify only the ARN of an IAM user. You cannot specify the ARN of an assumed role, federated user, or a service principal.

  

``--context-entries`` (list)


  A list of context keys and corresponding values for the simulation to use. Whenever a context key is evaluated by a ``Condition`` element in one of the simulated IAM permission policies, the corresponding value is supplied.

  



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

   

  Each of the EC2 scenarios requires that you specify instance, image, and security-group resources. If your scenario includes an EBS volume, then you must specify that volume as a resource. If the EC2 scenario includes VPC, then you must supply the network-interface resource. If it includes an IP subnet, then you must specify the subnet resource. For more information on the EC2 scenario options, see `Supported Platforms`_ in the *AWS EC2 User Guide* .

   

   
  * **EC2-Classic-InstanceStore**  instance, image, security-group 
   
  * **EC2-Classic-EBS**  instance, image, security-group, volume 
   
  * **EC2-VPC-InstanceStore**  instance, image, security-group, network-interface 
   
  * **EC2-VPC-InstanceStore-Subnet**  instance, image, security-group, network-interface, subnet 
   
  * **EC2-VPC-EBS**  instance, image, security-group, network-interface, volume 
   
  * **EC2-VPC-EBS-Subnet**  instance, image, security-group, network-interface, subnet, volume 
   

  

``--max-items`` (integer)


  Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

   

  This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from. 

  

``--marker`` (string)


  Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

EvaluationResults -> (list)

  

  The results of the simulation.

  

  (structure)

    

    Contains the results of a simulation.

     

    This data type is used by the return parameter of `` SimulatePolicy`` .

    

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

         

        This data type is used by the ``MatchedStatements`` member of the `` EvaluationResult`` type.

        

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

      

      A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. To discover the context keys used by a set of policies, you can call  get-context-keys-for-custom-policy or  get-context-keys-for-principal-policy .

        

      If the response includes any keys in this list, then the reported results might be untrustworthy because the simulation could not completely evaluate all of the conditions specified in the policies that would occur in a real world request.

       

      (string)

        

        

      

    EvalDecisionDetails -> (map)

      

      Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access. See `How IAM Roles Differ from Resource-based Policies`_ 

      

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

             

            This data type is used by the ``MatchedStatements`` member of the `` EvaluationResult`` type.

            

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

          

          A list of context keys that are required by the included input policies but that were not provided by one of the input parameters. To discover the context keys used by a set of policies, you can call  get-context-keys-for-custom-policy or  get-context-keys-for-principal-policy .

          

          (string)

            

            

          

        EvalDecisionDetails -> (map)

          

          Additional details about the results of the evaluation decision. When there are both IAM policies and resource policies, this parameter explains how each set of policies contributes to the final evaluation decision. When simulating cross-account access to a resource, both the resource-based policy and the caller's IAM policy must grant access.

          

          key -> (string)

            

            

          value -> (string)

            

            

          

        

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _GetFederationToken: http://docs.aws.amazon.com/IAM/latest/APIReference/API_GetFederationToken.html
.. _Supported Platforms: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-supported-platforms.html
.. _AssumeRole: http://docs.aws.amazon.com/IAM/latest/APIReference/API_AssumeRole.html
.. _How IAM Roles Differ from Resource-based Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_compare-resource-policies.html
