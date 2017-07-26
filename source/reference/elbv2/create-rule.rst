[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 create-rule:


***********
create-rule
***********



===========
Description
===========



Creates a rule for the specified listener.

 

Each rule can have one action and one condition. Rules are evaluated in priority order, from the lowest value to the highest value. When the condition for a rule is met, the specified action is taken. If no conditions are met, the default action for the default rule is taken. For more information, see `Listener Rules <http://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html#listener-rules>`_ in the *Application Load Balancers Guide* .

 

To view your current rules, use  describe-rules . To update a rule, use  modify-rule . To set the priorities of your rules, use  set-rule-priorities . To delete a rule, use  delete-rule .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/CreateRule>`_


========
Synopsis
========

::

    create-rule
  --listener-arn <value>
  --conditions <value>
  --priority <value>
  --actions <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--listener-arn`` (string)


  The Amazon Resource Name (ARN) of the listener.

  

``--conditions`` (list)


  A condition. Each condition specifies a field name and a single value.

   

  If the field name is ``host-header`` , you can specify a single host name (for example, my.example.com). A host name is case insensitive, can be up to 128 characters in length, and can contain any of the following characters. Note that you can include up to three wildcard characters.

   

   
  * A-Z, a-z, 0-9 
   
  * - . 
   
  * * (matches 0 or more characters) 
   
  * ? (matches exactly 1 character) 
   

   

  If the field name is ``path-pattern`` , you can specify a single path pattern. A path pattern is case sensitive, can be up to 128 characters in length, and can contain any of the following characters. Note that you can include up to three wildcard characters.

   

   
  * A-Z, a-z, 0-9 
   
  * _ - . $ / ~ " ' @ : + 
   
  * (using amp;) 
   
  * * (matches 0 or more characters) 
   
  * ? (matches exactly 1 character) 
   

  



Shorthand Syntax::

    Field=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Field": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--priority`` (integer)


  The priority for the rule. A listener can't have multiple rules with the same priority.

  

``--actions`` (list)


  An action. Each action has the type ``forward`` and specifies a target group.

  



Shorthand Syntax::

    Type=string,TargetGroupArn=string ...




JSON Syntax::

  [
    {
      "Type": "forward",
      "TargetGroupArn": "string"
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

**To create a rule**

This example creates a rule that forwards requests to the specified target group if the URL contains the specified pattern (for example, /img/*).

Command::

  aws elbv2 create-rule --listener-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:listener/app/my-load-balancer/50dc6c495c0c9188/f2f7dc8efc522ab2 --priority 10 --conditions Field=path-pattern,Values='/img/*' --actions Type=forward,TargetGroupArn=arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067

Output::

  {
    "Rules": [
        {
            "Priority": "10",
            "Conditions": [
                {
                    "Field": "path-pattern",
                    "Values": [
                        "/img/*"
                    ]
                }
            ],
            "RuleArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:listener-rule/app/my-load-balancer/50dc6c495c0c9188/f2f7dc8efc522ab2/9683b2d02a6cabee",
            "IsDefault": false,
            "Actions": [
                {
                    "TargetGroupArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067",
                    "Type": "forward"
                }
            ]
        }
    ]
  }


======
Output
======

Rules -> (list)

  

  Information about the rule.

  

  (structure)

    

    Information about a rule.

    

    RuleArn -> (string)

      

      The Amazon Resource Name (ARN) of the rule.

      

      

    Priority -> (string)

      

      The priority.

      

      

    Conditions -> (list)

      

      The conditions.

      

      (structure)

        

        Information about a condition for a rule.

        

        Field -> (string)

          

          The name of the field. The possible values are ``host-header`` and ``path-pattern`` .

          

          

        Values -> (list)

          

          The condition value.

           

          If the field name is ``host-header`` , you can specify a single host name (for example, my.example.com). A host name is case insensitive, can be up to 128 characters in length, and can contain any of the following characters. Note that you can include up to three wildcard characters.

           

           
          * A-Z, a-z, 0-9 
           
          * - . 
           
          * * (matches 0 or more characters) 
           
          * ? (matches exactly 1 character) 
           

           

          If the field name is ``path-pattern`` , you can specify a single path pattern (for example, /img/*). A path pattern is case sensitive, can be up to 128 characters in length, and can contain any of the following characters. Note that you can include up to three wildcard characters.

           

           
          * A-Z, a-z, 0-9 
           
          * _ - . $ / ~ " ' @ : + 
           
          * (using amp;) 
           
          * * (matches 0 or more characters) 
           
          * ? (matches exactly 1 character) 
           

          

          (string)

            

            

          

        

      

    Actions -> (list)

      

      The actions.

      

      (structure)

        

        Information about an action.

        

        Type -> (string)

          

          The type of action.

          

          

        TargetGroupArn -> (string)

          

          The Amazon Resource Name (ARN) of the target group.

          

          

        

      

    IsDefault -> (boolean)

      

      Indicates whether this is the default rule.

      

      

    

  

