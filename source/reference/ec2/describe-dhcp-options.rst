[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-dhcp-options:


*********************
describe-dhcp-options
*********************



===========
Description
===========



Describes one or more of your DHCP options sets.

 

For more information about DHCP options sets, see `DHCP Options Sets <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_DHCP_Options.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeDhcpOptions>`_


========
Synopsis
========

::

    describe-dhcp-options
  [--dhcp-options-ids <value>]
  [--filters <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dhcp-options-ids`` (list)


  The IDs of one or more DHCP options sets.

   

  Default: Describes all your DHCP options sets.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``dhcp-options-id`` - The ID of a set of DHCP options. 
   
  * ``key`` - The key for one of the options (for example, ``domain-name`` ). 
   
  * ``value`` - The value for one of the options. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   

  



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



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your DHCP options sets**

This example describes your DHCP options sets.

Command::

  aws ec2 describe-dhcp-options

Output::

  {
      "DhcpOptions": [
          {
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
          },
          {
              "DhcpConfigurations": [
                  {
                      "Values": [
                          "AmazonProvidedDNS"
                      ],
                      "Key": "domain-name-servers"
                  }
              ],
              "DhcpOptionsId": "dopt-7a8b9c2d"
          }
      ]  
  }

======
Output
======

DhcpOptions -> (list)

  

  Information about one or more DHCP options sets.

  

  (structure)

    

    Describes a set of DHCP options.

    

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

          

          

        

      

    

  

