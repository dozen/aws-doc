[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses list-configuration-sets:


***********************
list-configuration-sets
***********************



===========
Description
===========



Lists the configuration sets associated with your AWS account.

 

Configuration sets enable you to publish email sending events. For information about using configuration sets, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/monitor-sending-activity.html>`_ .

 

This action is throttled at one request per second and can return up to 50 configuration sets at a time.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/ListConfigurationSets>`_


========
Synopsis
========

::

    list-configuration-sets
  [--next-token <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  A token returned from a previous call to ``list-configuration-sets`` to indicate the position of the configuration set in the configuration set list.

  

``--max-items`` (integer)


  The number of configuration sets to return.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ConfigurationSets -> (list)

  

  A list of configuration sets.

  

  (structure)

    

    The name of the configuration set.

     

    Configuration sets enable you to publish email sending events. For information about using configuration sets, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/monitor-sending-activity.html>`_ .

    

    Name -> (string)

      

      The name of the configuration set. The name must:

       

       
      * Contain only ASCII letters (a-z, A-Z), numbers (0-9), underscores (_), or dashes (-). 
       
      * Contain less than 64 characters. 
       

      

      

    

  

NextToken -> (string)

  

  A token indicating that there are additional configuration sets available to be listed. Pass this token to successive calls of ``list-configuration-sets`` . 

  

  

