[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-spot-datafeed-subscription:


***********************************
describe-spot-datafeed-subscription
***********************************



===========
Description
===========



Describes the data feed for Spot instances. For more information, see `Spot Instance Data Feed`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    describe-spot-datafeed-subscription
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe Spot Instance datafeed subscription for an account**

This example command describes the data feed for the the account.

Command::

  aws ec2 describe-spot-datafeed-subscription

Output::

  {
      "SpotDatafeedSubscription": {
          "OwnerId": "<account-id>",
          "Prefix": "spotdata",
          "Bucket": "<s3-bucket-name>",
          "State": "Active"
      }
  }



======
Output
======

SpotDatafeedSubscription -> (structure)

  

  The Spot instance data feed subscription.

  

  OwnerId -> (string)

    

    The AWS account ID of the account.

    

    

  Bucket -> (string)

    

    The Amazon S3 bucket where the Spot instance data feed is located.

    

    

  Prefix -> (string)

    

    The prefix that is prepended to data feed files.

    

    

  State -> (string)

    

    The state of the Spot instance data feed subscription.

    

    

  Fault -> (structure)

    

    The fault codes for the Spot instance request, if any.

    

    Code -> (string)

      

      The reason code for the Spot instance state change.

      

      

    Message -> (string)

      

      The message for the Spot instance state change.

      

      

    

  



.. _Spot Instance Data Feed: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-data-feeds.html
