[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-security-groups:


***************************
describe-db-security-groups
***************************



===========
Description
===========



Returns a list of ``DBSecurityGroup`` descriptions. If a ``DBSecurityGroupName`` is specified, the list will contain only the descriptions of the specified DB security group. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeDBSecurityGroups>`_


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
  [--generate-cli-skeleton <value>]




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

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

          

          

        

      

    DBSecurityGroupArn -> (string)

      

      The Amazon Resource Name (ARN) for the DB security group.

      

      

    

  

