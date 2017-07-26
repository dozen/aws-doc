[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-spot-datafeed-subscription:


***********************************
describe-spot-datafeed-subscription
***********************************



===========
Description
===========



Describes the data feed for Spot instances. For more information, see `Spot Instance Data Feed <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-data-feeds.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeSpotDatafeedSubscription>`_


========
Synopsis
========

::

    describe-spot-datafeed-subscription
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe Spot Instance datafeed subscription for an account**

This example command describes the data feed for the account.

Command::

  aws ec2 describe-spot-datafeed-subscription

Output::

  {
      "SpotDatafeedSubscription": {
          "OwnerId": "123456789012",
          "Prefix": "spotdata",
          "Bucket": "my-s3-bucket",
          "State": "Active"
      }
  }



======
Output
======

SpotDatafeedSubscription -> (structure)

  

  The Spot instance data feed subscription.

  

  Bucket -> (string)

    

    The Amazon S3 bucket where the Spot instance data feed is located.

    

    

  Fault -> (structure)

    

    The fault codes for the Spot instance request, if any.

    

    Code -> (string)

      

      The reason code for the Spot instance state change.

      

      

    Message -> (string)

      

      The message for the Spot instance state change.

      

      

    

  OwnerId -> (string)

    

    The AWS account ID of the account.

    

    

  Prefix -> (string)

    

    The prefix that is prepended to data feed files.

    

    

  State -> (string)

    

    The state of the Spot instance data feed subscription.

    

    

  

