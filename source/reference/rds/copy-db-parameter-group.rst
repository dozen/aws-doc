[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds copy-db-parameter-group:


***********************
copy-db-parameter-group
***********************



===========
Description
===========



Copies the specified DB parameter group. 



========
Synopsis
========

::

    copy-db-parameter-group
  --source-db-parameter-group-identifier <value>
  --target-db-parameter-group-identifier <value>
  --target-db-parameter-group-description <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--source-db-parameter-group-identifier`` (string)


  The identifier or ARN for the source DB parameter group. For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN)`_ . 

   

  Constraints:

   

   
  * Must specify a valid DB parameter group.
   
  * If the source DB parameter group is in the same region as the copy, specify a valid DB parameter group identifier, for example ``my-db-param-group`` , or a valid ARN.
   
  * If the source DB parameter group is in a different region than the copy, specify a valid DB parameter group ARN, for example ``arn:aws:rds:us-west-2:123456789012:pg:special-parameters`` .
   

  

``--target-db-parameter-group-identifier`` (string)


  The identifier for the copied DB parameter group.

   

  Constraints:

   

   
  * Cannot be null, empty, or blank
   
  * Must contain from 1 to 255 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

   

  Example: ``my-db-parameter-group`` 

  

``--target-db-parameter-group-description`` (string)


  A description for the copied DB parameter group.

  

``--tags`` (list)


  A list of tags.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DBParameterGroup -> (structure)

  

  Contains the result of a successful invocation of the  create-db-parameter-group action. 

   

  This data type is used as a request parameter in the  delete-db-parameter-group action, and as a response element in the  describe-db-parameter-groups action. 

  

  DBParameterGroupName -> (string)

    

    Provides the name of the DB parameter group. 

    

    

  DBParameterGroupFamily -> (string)

    

    Provides the name of the DB parameter group family that this DB parameter group is compatible with. 

    

    

  Description -> (string)

    

    Provides the customer-specified description for this DB parameter group. 

    

    

  



.. _Constructing an RDS Amazon Resource Name (ARN): http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.html#USER_Tagging.ARN
