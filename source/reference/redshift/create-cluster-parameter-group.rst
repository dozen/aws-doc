[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift create-cluster-parameter-group:


******************************
create-cluster-parameter-group
******************************



===========
Description
===========



Creates an Amazon Redshift parameter group. 

 

Creating parameter groups is independent of creating clusters. You can associate a cluster with a parameter group when you create the cluster. You can also associate an existing cluster with a parameter group after the cluster is created by using  modify-cluster . 

 

Parameters in the parameter group define specific behavior that applies to the databases you create on the cluster. For more information about parameters and parameter groups, go to `Amazon Redshift Parameter Groups`_ in the *Amazon Redshift Cluster Management Guide* . 



========
Synopsis
========

::

    create-cluster-parameter-group
  --parameter-group-name <value>
  --parameter-group-family <value>
  --description <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--parameter-group-name`` (string)


  The name of the cluster parameter group. 

   

  Constraints: 

   

   
  * Must be 1 to 255 alphanumeric characters or hyphens
   
  * First character must be a letter.
   
  * Cannot end with a hyphen or contain two consecutive hyphens.
   
  * Must be unique withing your AWS account.
   

   

  .. note::

    This value is stored as a lower-case string.

  

``--parameter-group-family`` (string)


  The Amazon Redshift engine version to which the cluster parameter group applies. The cluster engine version determines the set of parameters. 

   

  To get a list of valid parameter group family names, you can call  describe-cluster-parameter-groups . By default, Amazon Redshift returns a list of all the parameter groups that are owned by your AWS account, including the default parameter groups for each Amazon Redshift engine version. The parameter group family names associated with the default parameter groups provide you the valid values. For example, a valid family name is "redshift-1.0". 

  

``--description`` (string)


  A description of the parameter group. 

  

``--tags`` (list)


  A list of tag instances.

  



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



========
Examples
========

Create a Cluster Parameter Group
--------------------------------

This example creates a new cluster parameter group.

Command::

   aws redshift create-cluster-parameter-group --parameter-group-name myclusterparametergroup --parameter-group-family redshift-1.0 --description "My first cluster parameter group"

Result::

    {
       "ClusterParameterGroup": {
          "ParameterGroupFamily": "redshift-1.0",
          "Description": "My first cluster parameter group",
          "ParameterGroupName": "myclusterparametergroup"
       },
       "ResponseMetadata": {
          "RequestId": "739448f0-64cc-11e2-8f7d-3b939af52818"
       }
    }




======
Output
======

ClusterParameterGroup -> (structure)

  

  Describes a parameter group.

  

  ParameterGroupName -> (string)

    

    The name of the cluster parameter group. 

    

    

  ParameterGroupFamily -> (string)

    

    The name of the cluster parameter group family that this cluster parameter group is compatible with. 

    

    

  Description -> (string)

    

    The description of the parameter group. 

    

    

  Tags -> (list)

    

    The list of tags for the cluster parameter group.

    

    (structure)

      

      A tag consisting of a name/value pair for a resource.

      

      Key -> (string)

        

        The key, or name, for the resource tag.

        

        

      Value -> (string)

        

        The value for the resource tag.

        

        

      

    

  



.. _Amazon Redshift Parameter Groups: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-parameter-groups.html
