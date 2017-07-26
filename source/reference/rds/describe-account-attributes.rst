[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-account-attributes:


***************************
describe-account-attributes
***************************



===========
Description
===========



Lists all of the attributes for a customer account. The attributes include Amazon RDS quotas for the account, such as the number of DB instances allowed. The description for a quota includes the quota name, current usage toward that quota, and the quota's maximum value.

 

This command does not take any parameters.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeAccountAttributes>`_


========
Synopsis
========

::

    describe-account-attributes
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AccountQuotas -> (list)

  

  A list of  AccountQuota objects. Within this list, each quota has a name, a count of usage toward the quota maximum, and a maximum value for the quota.

  

  (structure)

    

    Describes a quota for an AWS account, for example, the number of DB instances allowed.

    

    AccountQuotaName -> (string)

      

      The name of the Amazon RDS quota for this AWS account.

      

      

    Used -> (long)

      

      The amount currently used toward the quota maximum.

      

      

    Max -> (long)

      

      The maximum allowed value for the quota.

      

      

    

  

