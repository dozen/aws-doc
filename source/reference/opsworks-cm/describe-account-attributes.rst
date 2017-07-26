[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm describe-account-attributes:


***************************
describe-account-attributes
***************************



===========
Description
===========



Describes your account attributes, and creates requests to increase limits before they are reached or exceeded. 

 

This operation is synchronous. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/DescribeAccountAttributes>`_


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



========
Examples
========

**To describe account attributes**

The following ``describe-account-attributes`` command returns information about your
account's usage of AWS OpsWorks for Chef Automate resources.::

  aws opsworks-cm describe-account-attributes

The output for each account attribute entry returned by the command resembles the following.
*Output*::

  {
   "Attributes": [ 
      { 
         "Maximum": 5,
         "Name": "ServerLimit",
         "Used": 2
      }
   ]
  }

**More Information**

For more information, see `DescribeAccountAttributes`_ in the *AWS OpsWorks for Chef Automate API Reference*.

.. _`DescribeAccountAttributes`: http://docs.aws.amazon.com/opsworks-cm/latest/APIReference/API_DescribeAccountAttributes.html



======
Output
======

Attributes -> (list)

  

  The attributes that are currently set for the account. 

  

  (structure)

    

    Stores account attributes. 

    

    Name -> (string)

      

      The attribute name. The following are supported attribute names. 

       

       
      * *ServerLimit:* The number of current servers/maximum number of servers allowed. By default, you can have a maximum of 10 servers.  
       
      * *ManualBackupLimit:* The number of current manual backups/maximum number of backups allowed. By default, you can have a maximum of 50 manual backups saved.  
       

      

      

    Maximum -> (integer)

      

      The maximum allowed value. 

      

      

    Used -> (integer)

      

      The current usage, such as the current number of servers that are associated with the account. 

      

      

    

  

