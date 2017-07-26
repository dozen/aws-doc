[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-stale-security-groups:


******************************
describe-stale-security-groups
******************************



===========
Description
===========



[EC2-VPC only] Describes the stale security group rules for security groups in a specified VPC. Rules are stale when they reference a deleted security group in a peer VPC, or a security group in a peer VPC for which the VPC peering connection has been deleted.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeStaleSecurityGroups>`_


========
Synopsis
========

::

    describe-stale-security-groups
  [--dry-run | --no-dry-run]
  [--max-results <value>]
  [--next-token <value>]
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the operation, without actually making the request, and provides an error response. If you have the required permissions, the error response is DryRunOperation. Otherwise, it is UnauthorizedOperation.

  

``--max-results`` (integer)


  The maximum number of items to return for this request. The request returns a token that you can specify in a subsequent call to get the next set of results.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a prior call.)

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe stale security groups**

This example describes stale security group rules for ``vpc-11223344``. The response shows that sg-5fa68d3a in your account has a stale ingress SSH rule that references ``sg-279ab042`` in the peer VPC, and that ``sg-fe6fba9a`` in your account has a stale egress SSH rule that references ``sg-ef6fba8b`` in the peer VPC.

Command::

  aws ec2 describe-stale-security-groups --vpc-id vpc-11223344

Output::

  {
    "StaleSecurityGroupSet": [
        {
            "VpcId": "vpc-11223344", 
            "StaleIpPermissionsEgress": [
                {
                    "ToPort": 22, 
                    "FromPort": 22, 
                    "UserIdGroupPairs": [
                        {
                            "VpcId": "vpc-7a20e51f", 
                            "GroupId": "sg-ef6fba8b", 
                            "VpcPeeringConnectionId": "pcx-b04deed9", 
                            "PeeringStatus": "active"
                        }
                    ], 
                    "IpProtocol": "tcp"
                }
            ], 
            "GroupName": "MySG1", 
            "StaleIpPermissions": [], 
            "GroupId": "sg-fe6fba9a", 
            "Description": MySG1"
        }, 
        {
            "VpcId": "vpc-11223344", 
            "StaleIpPermissionsEgress": [], 
            "GroupName": "MySG2", 
            "StaleIpPermissions": [
                {
                    "ToPort": 22, 
                    "FromPort": 22, 
                    "UserIdGroupPairs": [
                        {
                            "VpcId": "vpc-7a20e51f", 
                            "GroupId": "sg-279ab042", 
                            "VpcPeeringConnectionId": "pcx-b04deed9", 
                            "PeeringStatus": "active"
                        }
                    ], 
                    "IpProtocol": "tcp"
                }
            ], 
            "GroupId": "sg-5fa68d3a", 
            "Description": "MySG2"
        }
    ]
  }

======
Output
======

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

StaleSecurityGroupSet -> (list)

  

  Information about the stale security groups.

  

  (structure)

    

    Describes a stale security group (a security group that contains stale rules).

    

    Description -> (string)

      

      The description of the security group.

      

      

    GroupId -> (string)

      

      The ID of the security group.

      

      

    GroupName -> (string)

      

      The name of the security group.

      

      

    StaleIpPermissions -> (list)

      

      Information about the stale inbound rules in the security group.

      

      (structure)

        

        Describes a stale rule in a security group.

        

        FromPort -> (integer)

          

          The start of the port range for the TCP and UDP protocols, or an ICMP type number. A value of ``-1`` indicates all ICMP types. 

          

          

        IpProtocol -> (string)

          

          The IP protocol name (for ``tcp`` , ``udp`` , and ``icmp`` ) or number (see `Protocol Numbers) <http://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml>`_ .

          

          

        IpRanges -> (list)

          

          One or more IP ranges. Not applicable for stale security group rules.

          

          (string)

            

            

          

        PrefixListIds -> (list)

          

          One or more prefix list IDs for an AWS service. Not applicable for stale security group rules.

          

          (string)

            

            

          

        ToPort -> (integer)

          

          The end of the port range for the TCP and UDP protocols, or an ICMP type number. A value of ``-1`` indicates all ICMP types. 

          

          

        UserIdGroupPairs -> (list)

          

          One or more security group pairs. Returns the ID of the referenced security group and VPC, and the ID and status of the VPC peering connection.

          

          (structure)

            

            Describes a security group and AWS account ID pair.

            

            GroupId -> (string)

              

              The ID of the security group.

              

              

            GroupName -> (string)

              

              The name of the security group. In a request, use this parameter for a security group in EC2-Classic or a default VPC only. For a security group in a nondefault VPC, use the security group ID.

              

              

            PeeringStatus -> (string)

              

              The status of a VPC peering connection, if applicable.

              

              

            UserId -> (string)

              

              The ID of an AWS account. For a referenced security group in another VPC, the account ID of the referenced security group is returned.

               

              [EC2-Classic] Required when adding or removing rules that reference a security group in another AWS account.

              

              

            VpcId -> (string)

              

              The ID of the VPC for the referenced security group, if applicable.

              

              

            VpcPeeringConnectionId -> (string)

              

              The ID of the VPC peering connection, if applicable.

              

              

            

          

        

      

    StaleIpPermissionsEgress -> (list)

      

      Information about the stale outbound rules in the security group.

      

      (structure)

        

        Describes a stale rule in a security group.

        

        FromPort -> (integer)

          

          The start of the port range for the TCP and UDP protocols, or an ICMP type number. A value of ``-1`` indicates all ICMP types. 

          

          

        IpProtocol -> (string)

          

          The IP protocol name (for ``tcp`` , ``udp`` , and ``icmp`` ) or number (see `Protocol Numbers) <http://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml>`_ .

          

          

        IpRanges -> (list)

          

          One or more IP ranges. Not applicable for stale security group rules.

          

          (string)

            

            

          

        PrefixListIds -> (list)

          

          One or more prefix list IDs for an AWS service. Not applicable for stale security group rules.

          

          (string)

            

            

          

        ToPort -> (integer)

          

          The end of the port range for the TCP and UDP protocols, or an ICMP type number. A value of ``-1`` indicates all ICMP types. 

          

          

        UserIdGroupPairs -> (list)

          

          One or more security group pairs. Returns the ID of the referenced security group and VPC, and the ID and status of the VPC peering connection.

          

          (structure)

            

            Describes a security group and AWS account ID pair.

            

            GroupId -> (string)

              

              The ID of the security group.

              

              

            GroupName -> (string)

              

              The name of the security group. In a request, use this parameter for a security group in EC2-Classic or a default VPC only. For a security group in a nondefault VPC, use the security group ID.

              

              

            PeeringStatus -> (string)

              

              The status of a VPC peering connection, if applicable.

              

              

            UserId -> (string)

              

              The ID of an AWS account. For a referenced security group in another VPC, the account ID of the referenced security group is returned.

               

              [EC2-Classic] Required when adding or removing rules that reference a security group in another AWS account.

              

              

            VpcId -> (string)

              

              The ID of the VPC for the referenced security group, if applicable.

              

              

            VpcPeeringConnectionId -> (string)

              

              The ID of the VPC peering connection, if applicable.

              

              

            

          

        

      

    VpcId -> (string)

      

      The ID of the VPC for the security group.

      

      

    

  

