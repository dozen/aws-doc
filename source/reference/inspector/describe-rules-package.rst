[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-rules-package:


**********************
describe-rules-package
**********************



===========
Description
===========



Describes the rules package specified by the rules package ARN.



========
Synopsis
========

::

    describe-rules-package
  --rules-package-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rules-package-arn`` (string)


  The ARN specifying the rules package that you want to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

rulesPackage -> (structure)

  

  Information about the rules package.

  

  rulesPackageArn -> (string)

    

    The ARN of the rules package.

    

    

  rulesPackageName -> (string)

    

    The name of the rules package.

    

    

  version -> (string)

    

    The version id of the rules package.

    

    

  provider -> (string)

    

    The provider of the rules package.

    

    

  description -> (structure)

    

    The description of the rules package.

    

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

          

          

        

      

    

  

