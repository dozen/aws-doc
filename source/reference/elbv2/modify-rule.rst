[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 modify-rule:


***********
modify-rule
***********



===========
Description
===========



Modifies the specified rule.

 

Any existing properties that you do not modify retain their current values.

 

To modify the default action, use  modify-listener .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/ModifyRule>`_


========
Synopsis
========

::

    modify-rule
  --rule-arn <value>
  [--conditions <value>]
  [--actions <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-arn`` (string)


  The Amazon Resource Name (ARN) of the rule.

  

``--conditions`` (list)


  The conditions.

  



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



``--actions`` (list)


  The actions.

  



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

**To modify a rule**

This example modifies the condition for the specified rule.

Command::

  aws elbv2 modify-rule --rule-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:listener-rule/app/my-load-balancer/50dc6c495c0c9188/f2f7dc8efc522ab2/9683b2d02a6cabee --conditions Field=path-pattern,Values='/images/*'

Output::

  {
    "Rules": [
        {
            "Priority": "10",
            "Conditions": [
                {
                    "Field": "path-pattern",
                    "Values": [
                        "/images/*"
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

      

      

    

  

