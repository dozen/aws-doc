[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-security-groups:


***************************
describe-db-security-groups
***************************



===========
Description
===========



Returns a list of ``DBSecurityGroup`` descriptions. If a ``DBSecurityGroupName`` is specified, the list will contain only the descriptions of the specified DB security group. 



``describe-db-security-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DBSecurityGroups``


========
Synopsis
========

::

    describe-db-security-groups
  [--db-security-group-name <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-security-group-name`` (string)


  The name of the DB security group to return details for. 

  

``--filters`` (list)


  This parameter is not currently supported.

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

DBSecurityGroups -> (list)

  

  A list of  DBSecurityGroup instances. 

  

  (structure)

    

    Contains the result of a successful invocation of the following actions: 

     

     
    *  describe-db-security-groups  
     
    *  authorize-db-security-group-ingress  
     
    *  create-db-security-group  
     
    *  revoke-db-security-group-ingress  
     

     

    This data type is used as a response element in the  describe-db-security-groups action.

    

    OwnerId -> (string)

      

      Provides the AWS ID of the owner of a specific DB security group. 

      

      

    DBSecurityGroupName -> (string)

      

      Specifies the name of the DB security group. 

      

      

    DBSecurityGroupDescription -> (string)

      

      Provides the description of the DB security group. 

      

      

    VpcId -> (string)

      

      Provides the VpcId of the DB security group. 

      

      

    EC2SecurityGroups -> (list)

      

      Contains a list of  EC2SecurityGroup elements. 

      

      (structure)

        

        This data type is used as a response element in the following actions: 

         

         
        *  authorize-db-security-group-ingress  
         
        *  describe-db-security-groups  
         
        *  revoke-db-security-group-ingress  
         

        

        Status -> (string)

          

          Provides the status of the EC2 security group. Status can be "authorizing", "authorized", "revoking", and "revoked". 

          

          

        EC2SecurityGroupName -> (string)

          

          Specifies the name of the EC2 security group. 

          

          

        EC2SecurityGroupId -> (string)

          

          Specifies the id of the EC2 security group. 

          

          

        EC2SecurityGroupOwnerId -> (string)

          

          Specifies the AWS ID of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` field. 

          

          

        

      

    IPRanges -> (list)

      

      Contains a list of  IPRange elements. 

      

      (structure)

        

        This data type is used as a response element in the  describe-db-security-groups action. 

        

        Status -> (string)

          

          Specifies the status of the IP range. Status can be "authorizing", "authorized", "revoking", and "revoked". 

          

          

        CIDRIP -> (string)

          

          Specifies the IP range. 

          

          

        

      

    

  

