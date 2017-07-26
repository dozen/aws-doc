[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-spot-datafeed-subscription:


*********************************
create-spot-datafeed-subscription
*********************************



===========
Description
===========



Creates a data feed for Spot instances, enabling you to view Spot instance usage logs. You can create one data feed per AWS account. For more information, see `Spot Instance Data Feed`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    create-spot-datafeed-subscription
  [--dry-run | --no-dry-run]
  --bucket <value>
  [--prefix <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--bucket`` (string)


  The Amazon S3 bucket in which to store the Spot instance data feed.

  

``--prefix`` (string)


  A prefix for the data feed file names.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a Spot Instance datafeed**

This example command creates a Spot Instance data feed for the account.

Command::

  aws ec2 create-spot-datafeed-subscription --bucket <s3-bucket-name> --prefix spotdata

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
