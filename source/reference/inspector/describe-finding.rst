[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-finding:


****************
describe-finding
****************



===========
Description
===========



Describes the finding specified by the finding ARN.



========
Synopsis
========

::

    describe-finding
  --finding-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--finding-arn`` (string)


  The ARN specifying the finding that you want to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

finding -> (structure)

  

  Information about the finding.

  

  findingArn -> (string)

    

    The ARN specifying the finding.

    

    

  runArn -> (string)

    

    The ARN of the assessment run that generated the finding.

    

    

  rulesPackageArn -> (string)

    

    The ARN of the rules package that is used to generate the finding.

    

    

  ruleName -> (string)

    

    The rule name that is used to generate the finding.

    

    

  agentId -> (string)

    

    The EC2 instance ID where the agent is installed that is used during the assessment that generates the finding. 

    

    

  autoScalingGroup -> (string)

    

    The autoscaling group of the EC2 instance where the agent is installed that is used during the assessment that generates the finding.

    

    

  severity -> (string)

    

    The finding severity. Values can be set to *High* , *Medium* , *Low* , and *Informational* .

    

    

  finding -> (structure)

    

    A short description that identifies the finding.

    

    key -> (structure)

      

      The facility and id properties of the  LocalizedTextKey data type.

      

      facility -> (string)

        

        The module response source of the text.

        

        

      id -> (string)

        

        Part of the module response source of the text.

        

        

      

    parameters -> (list)

      

      Values for the dynamic elements of the string specified by the textual identifier.

      

      (structure)

        

        This data type is used in the  LocalizedText data type.

        

        name -> (string)

          

          The name of the variable that is being replaced.

          

          

        value -> (string)

          

          The value assigned to the variable that is being replaced. 

          

          

        

      

    

  description -> (structure)

    

    The description of the finding.

    

    key -> (structure)

      

      The facility and id properties of the  LocalizedTextKey data type.

      

      facility -> (string)

        

        The module response source of the text.

        

        

      id -> (string)

        

        Part of the module response source of the text.

        

        

      

    parameters -> (list)

      

      Values for the dynamic elements of the string specified by the textual identifier.

      

      (structure)

        

        This data type is used in the  LocalizedText data type.

        

        name -> (string)

          

          The name of the variable that is being replaced.

          

          

        value -> (string)

          

          The value assigned to the variable that is being replaced. 

          

          

        

      

    

  recommendation -> (structure)

    

    The recommendation for the finding. 

    

    key -> (structure)

      

      The facility and id properties of the  LocalizedTextKey data type.

      

      facility -> (string)

        

        The module response source of the text.

        

        

      id -> (string)

        

        Part of the module response source of the text.

        

        

      

    parameters -> (list)

      

      Values for the dynamic elements of the string specified by the textual identifier.

      

      (structure)

        

        This data type is used in the  LocalizedText data type.

        

        name -> (string)

          

          The name of the variable that is being replaced.

          

          

        value -> (string)

          

          The value assigned to the variable that is being replaced. 

          

          

        

      

    

  attributes -> (list)

    

    The system-defined attributes for the finding. 

    

    (structure)

      

      This data type is used as a response element in the  add-attributes-to-findings action and a request parameter in the  create-assessment action.

      

      key -> (string)

        

        The attribute key.

        

        

      value -> (string)

        

        The value assigned to the attribute key.

        

        

      

    

  userAttributes -> (list)

    

    The user-defined attributes that are assigned to the finding.

    

    (structure)

      

      This data type is used as a response element in the  add-attributes-to-findings action and a request parameter in the  create-assessment action.

      

      key -> (string)

        

        The attribute key.

        

        

      value -> (string)

        

        The value assigned to the attribute key.

        

        

      

    

  

