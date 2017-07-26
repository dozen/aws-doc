[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-rules-packages:


*******************
list-rules-packages
*******************



===========
Description
===========



Lists all available Amazon Inspector rules packages.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/ListRulesPackages>`_


========
Synopsis
========

::

    list-rules-packages
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **list-rules-packages** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list rules packages**

The following ``list-rules-packages`` command lists all available Inspector rules packages::

  aws inspector list-rules-packages

Output::

 {
	"rulesPackageArns": [
	  "arn:aws:inspector:us-west-2:758058086616:rulespackage/0-9hgA516p",
	  "arn:aws:inspector:us-west-2:758058086616:rulespackage/0-H5hpSawc",
	  "arn:aws:inspector:us-west-2:758058086616:rulespackage/0-JJOtZiqQ",
	  "arn:aws:inspector:us-west-2:758058086616:rulespackage/0-vg5GGHSD"
	]
  }

For more information, see `Amazon Inspector Rules Packages and Rules`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Rules Packages and Rules`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_rule-packages.html


======
Output
======

rulesPackageArns -> (list)

  

  The list of ARNs that specifies the rules packages returned by the action.

  

  (string)

    

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

  

  

