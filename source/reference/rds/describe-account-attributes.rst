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



========
Synopsis
========

::

    describe-account-attributes
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      

    

  

