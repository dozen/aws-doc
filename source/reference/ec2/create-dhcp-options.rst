[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-dhcp-options:


*******************
create-dhcp-options
*******************



===========
Description
===========



Creates a set of DHCP options for your VPC. After creating the set, you must associate it with the VPC, causing all existing and new instances that you launch in the VPC to use this set of DHCP options. The following are the individual DHCP options you can specify. For more information about the options, see `RFC 2132 <http://www.ietf.org/rfc/rfc2132.txt>`_ .

 

 
* ``domain-name-servers`` - The IP addresses of up to four domain name servers, or AmazonProvidedDNS. The default DHCP option set specifies AmazonProvidedDNS. If specifying more than one domain name server, specify the IP addresses in a single parameter, separated by commas. If you want your instance to receive a custom DNS hostname as specified in ``domain-name`` , you must set ``domain-name-servers`` to a custom DNS server. 
 
* ``domain-name`` - If you're using AmazonProvidedDNS in ``us-east-1`` , specify ``ec2.internal`` . If you're using AmazonProvidedDNS in another region, specify ``region.compute.internal`` (for example, ``ap-northeast-1.compute.internal`` ). Otherwise, specify a domain name (for example, ``MyCompany.com`` ). This value is used to complete unqualified DNS hostnames. **Important** : Some Linux operating systems accept multiple domain names separated by spaces. However, Windows and other Linux operating systems treat the value as a single domain, which results in unexpected behavior. If your DHCP options set is associated with a VPC that has instances with multiple operating systems, specify only one domain name. 
 
* ``ntp-servers`` - The IP addresses of up to four Network Time Protocol (NTP) servers. 
 
* ``netbios-name-servers`` - The IP addresses of up to four NetBIOS name servers. 
 
* ``netbios-node-type`` - The NetBIOS node type (1, 2, 4, or 8). We recommend that you specify 2 (broadcast and multicast are not currently supported). For more information about these node types, see `RFC 2132 <http://www.ietf.org/rfc/rfc2132.txt>`_ . 
 

 

Your VPC automatically starts out with a set of DHCP options that includes only a DNS server that we provide (AmazonProvidedDNS). If you create a set of options, and if your VPC has an Internet gateway, make sure to set the ``domain-name-servers`` option either to ``AmazonProvidedDNS`` or to a domain name server of your choice. For more information about DHCP options, see `DHCP Options Sets <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_DHCP_Options.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateDhcpOptions>`_


========
Synopsis
========

::

    create-dhcp-options
  --dhcp-configurations <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dhcp-configurations`` (list)


  A DHCP configuration option.

  



Shorthand Syntax::

    Key=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a DHCP options set**

This example creates a DHCP options set.

Command::

  aws ec2 create-dhcp-options --dhcp-configuration "Key=domain-name-servers,Values=10.2.5.1,10.2.5.2"

Output::

  {
      "DhcpOptions": {
          "DhcpConfigurations": [
              {
                  "Values": [
                      "10.2.5.2",
                      "10.2.5.1"
                  ],
                  "Key": "domain-name-servers"
              }
          ],
          "DhcpOptionsId": "dopt-d9070ebb"
      }  
  }

======
Output
======

DhcpOptions -> (structure)

  

  A set of DHCP options.

  

  DhcpConfigurations -> (list)

    

    One or more DHCP options in the set.

    

    (structure)

      

      Describes a DHCP configuration option.

      

      Key -> (string)

        

        The name of a DHCP option.

        

        

      Values -> (list)

        

        One or more values for the DHCP option.

        

        (structure)

          

          Describes a value for a resource attribute that is a String.

          

          Value -> (string)

            

            The attribute value. Note that the value is case-sensitive.

            

            

          

        

      

    

  DhcpOptionsId -> (string)

    

    The ID of the set of DHCP options.

    

    

  Tags -> (list)

    

    Any tags assigned to the DHCP options set.

    

    (structure)

      

      Describes a tag.

      

      Key -> (string)

        

        The key of the tag.

         

        Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

        

        

      Value -> (string)

        

        The value of the tag.

         

        Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

        

        

      

    

  

