[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



Lists all tags associated with an assessment template.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/ListTagsForResource>`_


========
Synopsis
========

::

    list-tags-for-resource
  --resource-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The ARN that specifies the assessment template whose tags you want to list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list tags for resource**

The following ``list-tags-for-resource`` command lists all tags associated with the assessment template with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-gcwFliYu``::

  aws inspector list-tags-for-resource --resource-arn arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-gcwFliYu

Output::

   {
	 "tags": [
	   {
		 "key": "Name",
		 "value": "Example"
	   }
	 ]
   }

For more information, see `Amazon Inspector Assessment Templates and Assessment Runs`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Templates and Assessment Runs`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_assessments.html



======
Output
======

tags -> (list)

  

  A collection of key and value pairs.

  

  (structure)

    

    A key and value pair. This data type is used as a request parameter in the  set-tags-for-resource action and a response element in the  list-tags-for-resource action.

    

    key -> (string)

      

      A tag key.

      

      

    value -> (string)

      

      A value assigned to a tag key.

      

      

    

  

