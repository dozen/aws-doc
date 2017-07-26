[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-spot-datafeed-subscription:


*********************************
create-spot-datafeed-subscription
*********************************



===========
Description
===========



Creates a data feed for Spot instances, enabling you to view Spot instance usage logs. You can create one data feed per AWS account. For more information, see `Spot Instance Data Feed <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-data-feeds.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateSpotDatafeedSubscription>`_


========
Synopsis
========

::

    create-spot-datafeed-subscription
  --bucket <value>
  [--dry-run | --no-dry-run]
  [--prefix <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


  The Amazon S3 bucket in which to store the Spot instance data feed.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--prefix`` (string)


  A prefix for the data feed file names.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    

  

