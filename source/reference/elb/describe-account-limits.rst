[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb describe-account-limits:


***********************
describe-account-limits
***********************



===========
Description
===========



Describes the current Elastic Load Balancing resource limits for your AWS account.

 

For more information, see `Limits for Your Classic Load Balancer <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-limits.html>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/DescribeAccountLimits>`_


========
Synopsis
========

::

    describe-account-limits
  [--marker <value>]
  [--page-size <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--marker`` (string)


  The marker for the next set of results. (You received this marker from a previous call.)

  

``--page-size`` (integer)


  The maximum number of results to return with this call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Limits -> (list)

  

  Information about the limits.

  

  (structure)

    

    Information about an Elastic Load Balancing resource limit for your AWS account.

    

    Name -> (string)

      

      The name of the limit. The possible values are:

       

       
      * classic-listeners 
       
      * classic-load-balancers 
       

      

      

    Max -> (string)

      

      The maximum value of the limit.

      

      

    

  

NextMarker -> (string)

  

  The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

  

  

