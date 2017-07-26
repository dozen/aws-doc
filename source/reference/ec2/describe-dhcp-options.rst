[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-dhcp-options:


*********************
describe-dhcp-options
*********************



===========
Description
===========



Describes one or more of your DHCP options sets.

 

For more information about DHCP options sets, see `DHCP Options Sets`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    describe-dhcp-options
  [--dry-run | --no-dry-run]
  [--dhcp-options-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

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
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    DhcpOptionsId -> (string)

      

      The ID of the set of DHCP options.

      

      

    DhcpConfigurations -> (list)

      

      One or more DHCP options in the set.

      

      (structure)

        

        Describes a DHCP configuration option.

        

        Key -> (string)

          

          The name of a DHCP option.

          

          

        Values -> (list)

          

          One or more values for the DHCP option.

          

          (structure)

            

            The value to use for a resource attribute.

            

            Value -> (string)

              

              Valid values are case-sensitive and vary by action.

              

              

            

          

        

      

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

          

          

        

      

    

  



.. _DHCP Options Sets: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_DHCP_Options.html
