[ :ref:`aws <cli:aws>` . :ref:`sdb <cli:aws sdb>` ]

.. _cli:aws sdb list-domains:


************
list-domains
************



===========
Description
===========



The ``list-domains`` operation lists all domains associated with the Access Key ID. It returns domain names up to the limit set by `MaxNumberOfDomains`_ . A `NextToken`_ is returned if there are more than ``MaxNumberOfDomains`` domains. Calling ``list-domains`` successive times with the ``NextToken`` provided by the operation returns up to ``MaxNumberOfDomains`` more domain names with each successive operation call. 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.sdb true`` 



``list-domains`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DomainNames``


========
Synopsis
========

::

    list-domains
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DomainNames -> (list)

  A list of domain names that match the expression.

  (string)

    

    

  

NextToken -> (string)

  An opaque token indicating that there are more domains than the specified ``MaxNumberOfDomains`` still available.

  



.. _MaxNumberOfDomains: #MaxNumberOfDomains
.. _NextToken: #NextToken
