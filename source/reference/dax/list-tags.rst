[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax list-tags:


*********
list-tags
*********



===========
Description
===========



List all of the tags for a DAX cluster. You can call ``list-tags`` up to 10 times per second, per account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/ListTags>`_


========
Synopsis
========

::

    list-tags
  --resource-name <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-name`` (string)


  The name of the DAX resource to which the tags belong.

  

``--next-token`` (string)


  An optional token returned from a prior request. Use this token for pagination of results from this action. If this parameter is specified, the response includes only results beyond the token.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Tags -> (list)

  

  A list of tags currently associated with the DAX cluster.

  

  (structure)

    

    A description of a tag. Every tag is a key-value pair. You can add up to 50 tags to a single DAX cluster.

     

    AWS-assigned tag names and values are automatically assigned the ``aws:`` prefix, which the user cannot assign. AWS-assigned tag names do not count towards the tag limit of 50. User-assigned tag names have the prefix ``user:`` .

     

    You cannot backdate the application of a tag.

    

    Key -> (string)

      

      The key for the tag. Tag keys are case sensitive. Every DAX cluster can only have one tag with the same key. If you try to add an existing tag (same key), the existing tag value will be updated to the new value.

      

      

    Value -> (string)

      

      The value of the tag. Tag values are case-sensitive and can be null. 

      

      

    

  

NextToken -> (string)

  

  If this value is present, there are additional results to be displayed. To retrieve them, call ``list-tags`` again, with ``NextToken`` set to this value.

  

  

