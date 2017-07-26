[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift get-cluster-credentials:


***********************
get-cluster-credentials
***********************



===========
Description
===========



Returns a database user name and temporary password with temporary authorization to log in to an Amazon Redshift database. The action returns the database user name prefixed with ``IAM:`` if ``AutoCreate`` is ``False`` or ``IAMA:`` if ``AutoCreate`` is ``True`` . You can optionally specify one or more database user groups that the user will join at log in. By default, the temporary credentials expire in 900 seconds. You can optionally specify a duration between 900 seconds (15 minutes) and 3600 seconds (60 minutes). For more information, see Generating IAM Database User Credentials in the Amazon Redshift Cluster Management Guide.

 

The IAM user or role that executes get-cluster-credentials must have an IAM policy attached that allows the ``redshift:GetClusterCredentials`` action with access to the ``dbuser`` resource on the cluster. The user name specified for ``dbuser`` in the IAM policy and the user name specified for the ``DbUser`` parameter must match.

 

If the ``DbGroups`` parameter is specified, the IAM policy must allow the ``redshift:JoinGroup`` action with access to the listed ``dbgroups`` . 

 

In addition, if the ``AutoCreate`` parameter is set to ``True`` , then the policy must include the ``redshift:CreateClusterUser`` privilege.

 

If the ``DbName`` parameter is specified, the IAM policy must allow access to the resource ``dbname`` for the specified database name. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/GetClusterCredentials>`_


========
Synopsis
========

::

    get-cluster-credentials
  --db-user <value>
  [--db-name <value>]
  --cluster-identifier <value>
  [--duration-seconds <value>]
  [--auto-create | --no-auto-create]
  [--db-groups <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-user`` (string)


  The name of a database user. If a user name matching ``DbUser`` exists in the database, the temporary user credentials have the same permissions as the existing user. If ``DbUser`` doesn't exist in the database and ``Autocreate`` is ``True`` , a new user is created using the value for ``DbUser`` with PUBLIC permissions. If a database user matching the value for ``DbUser`` doesn't exist and ``Autocreate`` is ``False`` , then the command succeeds but the connection attempt will fail because the user doesn't exist in the database.

   

  For more information, see `CREATE USER <http://docs.aws.amazon.com/http:/docs.aws.amazon.com/redshift/latest/dg/r_CREATE_USER.html>`_ in the Amazon Redshift Database Developer Guide. 

   

  Constraints:

   

   
  * Must be 1 to 128 alphanumeric characters or hyphens 
   
  * Must contain only lowercase letters. 
   
  * First character must be a letter. 
   
  * Must not contain a colon ( : ) or slash ( / ).  
   
  * Cannot be a reserved word. A list of reserved words can be found in `Reserved Words <http://docs.aws.amazon.com/redshift/latest/dg/r_pg_keywords.html>`_ in the Amazon Redshift Database Developer Guide. 
   

  

``--db-name`` (string)


  The name of a database that ``DbUser`` is authorized to log on to. If ``DbName`` is not specified, ``DbUser`` can log in to any existing database.

   

  Constraints:

   

   
  * Must be 1 to 64 alphanumeric characters or hyphens 
   
  * Must contain only lowercase letters. 
   
  * Cannot be a reserved word. A list of reserved words can be found in `Reserved Words <http://docs.aws.amazon.com/redshift/latest/dg/r_pg_keywords.html>`_ in the Amazon Redshift Database Developer Guide. 
   

  

``--cluster-identifier`` (string)


  The unique identifier of the cluster that contains the database for which your are requesting credentials. This parameter is case sensitive.

  

``--duration-seconds`` (integer)


  The number of seconds until the returned temporary password expires.

   

  Constraint: minimum 900, maximum 3600.

   

  Default: 900

  

``--auto-create`` | ``--no-auto-create`` (boolean)


  Create a database user with the name specified for ``DbUser`` if one does not exist.

  

``--db-groups`` (list)


  A list of the names of existing database groups that ``DbUser`` will join for the current session. If not specified, the new user is added only to PUBLIC.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DbUser -> (string)

  

  A database user name that is authorized to log on to the database ``DbName`` using the password ``DbPassword`` . If the ``DbGroups`` parameter is specifed, ``DbUser`` is added to the listed groups for the current session. The user name is prefixed with ``IAM:`` for an existing user name or ``IAMA:`` if the user was auto-created. 

  

  

DbPassword -> (string)

  

  A temporary password that authorizes the user name returned by ``DbUser`` to log on to the database ``DbName`` . 

  

  

Expiration -> (timestamp)

  

  The date and time ``DbPassword`` expires.

  

  

