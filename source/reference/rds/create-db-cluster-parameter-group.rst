[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds create-db-cluster-parameter-group:


*********************************
create-db-cluster-parameter-group
*********************************



===========
Description
===========



Creates a new DB cluster parameter group.

 

Parameters in a DB cluster parameter group apply to all of the instances in a DB cluster.

 

A DB cluster parameter group is initially created with the default parameters for the database engine used by instances in the DB cluster. To provide custom values for any of the parameters, you must modify the group after creating it using  modify-db-cluster-parameter-group . Once you've created a DB cluster parameter group, you need to associate it with your DB cluster using  modify-db-cluster . When you associate a new DB cluster parameter group with a running DB cluster, you need to reboot the DB instances in the DB cluster without failover for the new DB cluster parameter group and associated settings to take effect. 

 

.. warning::

   

  After you create a DB cluster parameter group, you should wait at least 5 minutes before creating your first DB cluster that uses that DB cluster parameter group as the default parameter group. This allows Amazon RDS to fully complete the create action before the DB cluster parameter group is used as the default for a new DB cluster. This is especially important for parameters that are critical when creating the default database for a DB cluster, such as the character set for the default database defined by the ``character_set_database`` parameter. You can use the *Parameter Groups* option of the `Amazon RDS console <https://console.aws.amazon.com/rds/>`_ or the  describe-db-cluster-parameters command to verify that your DB cluster parameter group has been created or modified.

   

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html>`_ in the *Amazon RDS User Guide.*  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/CreateDBClusterParameterGroup>`_


========
Synopsis
========

::

    create-db-cluster-parameter-group
  --db-cluster-parameter-group-name <value>
  --db-parameter-group-family <value>
  --description <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-cluster-parameter-group-name`` (string)


  The name of the DB cluster parameter group.

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

   

  .. note::

     

    This value is stored as a lowercase string.

     

  

``--db-parameter-group-family`` (string)


  The DB cluster parameter group family name. A DB cluster parameter group can be associated with one and only one DB cluster parameter group family, and can be applied only to a DB cluster running a database engine and engine version compatible with that DB cluster parameter group family.

  

``--description`` (string)


  The description for the DB cluster parameter group.

  

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

    

    

  

