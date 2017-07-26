[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds add-ip-routes:


*************
add-ip-routes
*************



===========
Description
===========



If the DNS server for your on-premises domain uses a publicly addressable IP address, you must add a CIDR address block to correctly route traffic to and from your Microsoft AD on Amazon Web Services. *add-ip-routes* adds this address block. You can also use *add-ip-routes* to facilitate routing traffic that uses public IP ranges from your Microsoft AD on AWS to a peer VPC. 

 

Before you call *add-ip-routes* , ensure that all of the required permissions have been explicitly granted through a policy. For details about what permissions are required to run the *add-ip-routes* operation, see `AWS Directory Service API Permissions\: Actions, Resources, and Conditions Reference <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/UsingWithDS_IAM_ResourcePermissions.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/AddIpRoutes>`_


========
Synopsis
========

::

    add-ip-routes
  --directory-id <value>
  --ip-routes <value>
  [--update-security-group-for-directory-controllers | --no-update-security-group-for-directory-controllers]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  Identifier (ID) of the directory to which to add the address block.

  

``--ip-routes`` (list)


  IP address blocks, using CIDR format, of the traffic to route. This is often the IP address block of the DNS server used for your on-premises domain.

  



Shorthand Syntax::

    CidrIp=string,Description=string ...




JSON Syntax::

  [
    {
      "CidrIp": "string",
      "Description": "string"
    }
    ...
  ]



``--update-security-group-for-directory-controllers`` | ``--no-update-security-group-for-directory-controllers`` (boolean)


  If set to true, updates the inbound and outbound rules of the security group that has the description: "AWS created security group for *directory ID* directory controllers." Following are the new rules: 

   

  Inbound:

   

   
  * Type: Custom UDP Rule, Protocol: UDP, Range: 88, Source: 0.0.0.0/0 
   
  * Type: Custom UDP Rule, Protocol: UDP, Range: 123, Source: 0.0.0.0/0 
   
  * Type: Custom UDP Rule, Protocol: UDP, Range: 138, Source: 0.0.0.0/0 
   
  * Type: Custom UDP Rule, Protocol: UDP, Range: 389, Source: 0.0.0.0/0 
   
  * Type: Custom UDP Rule, Protocol: UDP, Range: 464, Source: 0.0.0.0/0 
   
  * Type: Custom UDP Rule, Protocol: UDP, Range: 445, Source: 0.0.0.0/0 
   
  * Type: Custom TCP Rule, Protocol: TCP, Range: 88, Source: 0.0.0.0/0 
   
  * Type: Custom TCP Rule, Protocol: TCP, Range: 135, Source: 0.0.0.0/0 
   
  * Type: Custom TCP Rule, Protocol: TCP, Range: 445, Source: 0.0.0.0/0 
   
  * Type: Custom TCP Rule, Protocol: TCP, Range: 464, Source: 0.0.0.0/0 
   
  * Type: Custom TCP Rule, Protocol: TCP, Range: 636, Source: 0.0.0.0/0 
   
  * Type: Custom TCP Rule, Protocol: TCP, Range: 1024-65535, Source: 0.0.0.0/0 
   
  * Type: Custom TCP Rule, Protocol: TCP, Range: 3268-33269, Source: 0.0.0.0/0 
   
  * Type: DNS (UDP), Protocol: UDP, Range: 53, Source: 0.0.0.0/0 
   
  * Type: DNS (TCP), Protocol: TCP, Range: 53, Source: 0.0.0.0/0 
   
  * Type: LDAP, Protocol: TCP, Range: 389, Source: 0.0.0.0/0 
   
  * Type: All ICMP, Protocol: All, Range: N/A, Source: 0.0.0.0/0 
   

   

  

   

  Outbound:

   

   
  * Type: All traffic, Protocol: All, Range: All, Destination: 0.0.0.0/0 
   

   

  These security rules impact an internal network interface that is not exposed publicly.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

