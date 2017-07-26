[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses list-receipt-rule-sets:


**********************
list-receipt-rule-sets
**********************



===========
Description
===========



Lists the receipt rule sets that exist under your AWS account. If there are additional receipt rule sets to be retrieved, you will receive a ``next-token`` that you can provide to the next call to ``list-receipt-rule-sets`` to retrieve the additional entries.

 

For information about managing receipt rule sets, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-managing-receipt-rule-sets.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/ListReceiptRuleSets>`_


========
Synopsis
========

::

    list-receipt-rule-sets
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  A token returned from a previous call to ``list-receipt-rule-sets`` to indicate the position in the receipt rule set list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

RuleSets -> (list)

  

  The metadata for the currently active receipt rule set. The metadata consists of the rule set name and the timestamp of when the rule set was created.

  

  (structure)

    

    Information about a receipt rule set.

     

    A receipt rule set is a collection of rules that specify what Amazon SES should do with mail it receives on behalf of your account's verified domains.

     

    For information about setting up receipt rule sets, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-receipt-rule-set.html>`_ .

    

    Name -> (string)

      

      The name of the receipt rule set. The name must:

       

       
      * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-). 
       
      * Start and end with a letter or number. 
       
      * Contain less than 64 characters. 
       

      

      

    CreatedTimestamp -> (timestamp)

      

      The date and time the receipt rule set was created.

      

      

    

  

NextToken -> (string)

  

  A token indicating that there are additional receipt rule sets available to be listed. Pass this token to successive calls of ``list-receipt-rule-sets`` to retrieve up to 100 receipt rule sets at a time.

  

  

