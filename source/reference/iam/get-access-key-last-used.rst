[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-access-key-last-used:


************************
get-access-key-last-used
************************



===========
Description
===========



Retrieves information about when the specified access key was last used. The information includes the date and time of last use, along with the AWS service and region that were specified in the last request made with that key.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetAccessKeyLastUsed>`_


========
Synopsis
========

::

    get-access-key-last-used
  --access-key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--access-key-id`` (string)


  The identifier of an access key.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters that can consist of any upper or lowercased letter or digit.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To retrieve information about when the specified access key was last used**

The following example retrieves information about when the access key ``ABCDEXAMPLE`` was last used::

  aws iam get-access-key-last-used --access-key-id ABCDEXAMPLE


Output::

  {
    "UserName":  "Bob",
    "AccessKeyLastUsed": {
        "Region": "us-east-1",
        "ServiceName": "iam",
        "LastUsedDate": "2015-06-16T22:45:00Z"
    }
  }

For more information, see `Managing Access Keys for IAM Users`_ in the *Using IAM* guide.

.. _`Managing Access Keys for IAM Users`: http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingCredentials.html

======
Output
======

UserName -> (string)

  

  The name of the AWS IAM user that owns this access key.

   

  

  

  

AccessKeyLastUsed -> (structure)

  

  Contains information about the last time the access key was used.

  

  LastUsedDate -> (timestamp)

    

    The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the access key was most recently used. This field is null when:

     

     
    * The user does not have an access key. 
     
    * An access key exists but has never been used, at least not since IAM started tracking this information on April 22nd, 2015. 
     
    * There is no sign-in data associated with the user 
     

    

    

  ServiceName -> (string)

    

    The name of the AWS service with which this access key was most recently used. This field displays "N/A" when:

     

     
    * The user does not have an access key. 
     
    * An access key exists but has never been used, at least not since IAM started tracking this information on April 22nd, 2015. 
     
    * There is no sign-in data associated with the user 
     

    

    

  Region -> (string)

    

    The AWS region where this access key was most recently used. This field is displays "N/A" when:

     

     
    * The user does not have an access key. 
     
    * An access key exists but has never been used, at least not since IAM started tracking this information on April 22nd, 2015. 
     
    * There is no sign-in data associated with the user 
     

     

    For more information about AWS regions, see `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html>`_ in the Amazon Web Services General Reference.

    

    

  

