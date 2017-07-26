[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds create-db-parameter-group:


*************************
create-db-parameter-group
*************************



===========
Description
===========



Creates a new DB parameter group.

 

A DB parameter group is initially created with the default parameters for the database engine used by the DB instance. To provide custom values for any of the parameters, you must modify the group after creating it using *modify-db-parameter-group* . Once you've created a DB parameter group, you need to associate it with your DB instance using *modify-db-instance* . When you associate a new DB parameter group with a running DB instance, you need to reboot the DB instance without failover for the new DB parameter group and associated settings to take effect. 

 

.. warning::

   

  After you create a DB parameter group, you should wait at least 5 minutes before creating your first DB instance that uses that DB parameter group as the default parameter group. This allows Amazon RDS to fully complete the create action before the parameter group is used as the default for a new DB instance. This is especially important for parameters that are critical when creating the default database for a DB instance, such as the character set for the default database defined by the ``character_set_database`` parameter. You can use the *Parameter Groups* option of the `Amazon RDS console <https://console.aws.amazon.com/rds/>`_ or the *describe-db-parameters* command to verify that your DB parameter group has been created or modified.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/CreateDBParameterGroup>`_


========
Synopsis
========

::

    create-db-parameter-group
  --db-parameter-group-name <value>
  --db-parameter-group-family <value>
  --description <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-parameter-group-name`` (string)


  The name of the DB parameter group.

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

   

  .. note::

     

    This value is stored as a lowercase string.

     

  

``--db-parameter-group-family`` (string)


  The DB parameter group family name. A DB parameter group can be associated with one and only one DB parameter group family, and can be applied only to a DB instance running a database engine and engine version compatible with that DB parameter group family.

  

``--description`` (string)


  The description for the DB parameter group.

  

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

DBParameterGroup -> (structure)

  

  Contains the result of a successful invocation of the  create-db-parameter-group action. 

   

  This data type is used as a request parameter in the  delete-db-parameter-group action, and as a response element in the  describe-db-parameter-groups action. 

  

  DBParameterGroupName -> (string)

    

    Provides the name of the DB parameter group.

    

    

  DBParameterGroupFamily -> (string)

    

    Provides the name of the DB parameter group family that this DB parameter group is compatible with.

    

    

  Description -> (string)

    

    Provides the customer-specified description for this DB parameter group.

    

    

  DBParameterGroupArn -> (string)

    

    The Amazon Resource Name (ARN) for the DB parameter group.

    

    

  

