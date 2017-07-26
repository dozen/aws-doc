[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-regions:


****************
describe-regions
****************



===========
Description
===========



Describes one or more regions that are currently available to you.

 

For a list of the regions supported by Amazon EC2, see `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html#ec2_region>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeRegions>`_


========
Synopsis
========

::

    describe-regions
  [--filters <value>]
  [--region-names <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``endpoint`` - The endpoint of the region (for example, ``ec2.us-east-1.amazonaws.com`` ). 
   
  * ``region-name`` - The name of the region (for example, ``us-east-1`` ). 
   

  



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



``--region-names`` (list)


  The names of one or more regions.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your regions**

This example describes all the regions that are available to you.

Command::

  aws ec2 describe-regions

Output::

  {
      "Regions": [
          {
              "Endpoint": "ec2.eu-west-1.amazonaws.com",
              "RegionName": "eu-west-1"
          },
          {
              "Endpoint": "ec2.ap-south-1.amazonaws.com",
              "RegionName": "ap-south-1"
          },
          {
              "Endpoint": "ec2.ap-southeast-1.amazonaws.com",
              "RegionName": "ap-southeast-1"
          },
          {
              "Endpoint": "ec2.ap-southeast-2.amazonaws.com",
              "RegionName": "ap-southeast-2"
          },
          {
              "Endpoint": "ec2.eu-central-1.amazonaws.com",
              "RegionName": "eu-central-1"
          },
          {
              "Endpoint": "ec2.ap-northeast-2.amazonaws.com",
              "RegionName": "ap-northeast-2"
          },
          {
              "Endpoint": "ec2.ap-northeast-1.amazonaws.com",
              "RegionName": "ap-northeast-1"
          },
          {
              "Endpoint": "ec2.us-east-1.amazonaws.com",
              "RegionName": "us-east-1"
          },
          {
              "Endpoint": "ec2.sa-east-1.amazonaws.com",
              "RegionName": "sa-east-1"
          },
          {
              "Endpoint": "ec2.us-west-1.amazonaws.com",
              "RegionName": "us-west-1"
          },
          {
              "Endpoint": "ec2.us-west-2.amazonaws.com",
              "RegionName": "us-west-2"
          }
      ]
  }

**To describe the regions with an endpoint that has a specific string**

This example describes all regions that are available to you that have the string "us" in the endpoint.

Command::

  aws ec2 describe-regions --filters "Name=endpoint,Values=*us*"

Output::

  {
      "Regions": [
          {
              "Endpoint": "ec2.us-east-1.amazonaws.com",
              "RegionName": "us-east-1"
          },
          {
              "Endpoint": "ec2.us-west-2.amazonaws.com",
              "RegionName": "us-west-2"
          },
          {
              "Endpoint": "ec2.us-west-1.amazonaws.com",
              "RegionName": "us-west-1"
          },
      ]
  }

**To describe region names only**

This example uses the ``--query`` parameter to filter the output and return the names of the regions only. The output is returned as tab-delimited lines.

Command::

  aws ec2 describe-regions --query 'Regions[].{Name:RegionName}' --output text
  
Output::

  ap-south-1
  eu-west-1
  ap-southeast-1
  ap-southeast-2
  eu-central-1
  ap-northeast-2
  ap-northeast-1
  us-east-1
  sa-east-1
  us-west-1
  us-west-2


======
Output
======

Regions -> (list)

  

  Information about one or more regions.

  

  (structure)

    

    Describes a region.

    

    Endpoint -> (string)

      

      The region service endpoint.

      

      

    RegionName -> (string)

      

      The name of the region.

      

      

    

  

