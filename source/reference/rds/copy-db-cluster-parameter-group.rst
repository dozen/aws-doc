[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds copy-db-cluster-parameter-group:


*******************************
copy-db-cluster-parameter-group
*******************************



===========
Description
===========



Copies the specified DB cluster parameter group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/CopyDBClusterParameterGroup>`_


========
Synopsis
========

::

    copy-db-cluster-parameter-group
  --source-db-cluster-parameter-group-identifier <value>
  --target-db-cluster-parameter-group-identifier <value>
  --target-db-cluster-parameter-group-description <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-db-cluster-parameter-group-identifier`` (string)


  The identifier or Amazon Resource Name (ARN) for the source DB cluster parameter group. For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN) <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.ARN.html#USER_Tagging.ARN.Constructing>`_ . 

   

  Constraints:

   

   
  * Must specify a valid DB cluster parameter group. 
   
  * If the source DB cluster parameter group is in the same region as the copy, specify a valid DB parameter group identifier, for example ``my-db-cluster-param-group`` , or a valid ARN. 
   
  * If the source DB parameter group is in a different region than the copy, specify a valid DB cluster parameter group ARN, for example ``arn:aws:rds:us-east-1:123456789012:cluster-pg:custom-cluster-group1`` . 
   

  

``--target-db-cluster-parameter-group-identifier`` (string)


  The identifier for the copied DB cluster parameter group.

   

  Constraints:

   

   
  * Cannot be null, empty, or blank 
   
  * Must contain from 1 to 255 alphanumeric characters or hyphens 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

   

  Example: ``my-cluster-param-group1``  

  

``--target-db-cluster-parameter-group-description`` (string)


  A description for the copied DB cluster parameter group.

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DBClusterParameterGroup -> (structure)

  

  Contains the result of a successful invocation of the  create-db-cluster-parameter-group or  copy-db-cluster-parameter-group action. 

   

  This data type is used as a request parameter in the  delete-db-cluster-parameter-group action, and as a response element in the  describe-db-cluster-parameter-groups action. 

  

  DBClusterParameterGroupName -> (string)

    

    Provides the name of the DB cluster parameter group.

    

    

  DBParameterGroupFamily -> (string)

    

    Provides the name of the DB parameter group family that this DB cluster parameter group is compatible with.

    

    

  Description -> (string)

    

    Provides the customer-specified description for this DB cluster parameter group.

    

    

  DBClusterParameterGroupArn -> (string)

    

    The Amazon Resource Name (ARN) for the DB cluster parameter group.

    

    

  

