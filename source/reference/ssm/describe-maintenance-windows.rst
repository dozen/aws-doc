[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-maintenance-windows:


****************************
describe-maintenance-windows
****************************



===========
Description
===========



Retrieves the Maintenance Windows in an AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeMaintenanceWindows>`_


========
Synopsis
========

::

    describe-maintenance-windows
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  Optional filters used to narrow down the scope of the returned Maintenance Windows. Supported filter keys are Name and Enabled.

  



Shorthand Syntax::

    Key=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--max-results`` (integer)


  The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list all maintenance windows**

This example lists all maintenance windows on your account.

Command::

  aws ssm describe-maintenance-windows

Output::

  {
    "WindowIdentities": [
        {
            "Duration": 2,
            "Cutoff": 1,
            "WindowId": "mw-03eb9db42890fb82d",
            "Enabled": true,
            "Name": "TestMaintWin"
        },
    ]
  }

**To list all enabled maintenance windows**
  
This example lists all enabled maintenance windows.

Command::

  aws ssm describe-maintenance-windows --filters "Key=Enabled,Values=true"
  

======
Output
======

WindowIdentities -> (list)

  

  Information about the Maintenance Windows.

  

  (structure)

    

    Information about the Maintenance Window.

    

    WindowId -> (string)

      

      The ID of the Maintenance Window.

      

      

    Name -> (string)

      

      The name of the Maintenance Window.

      

      

    Enabled -> (boolean)

      

      Whether the Maintenance Window is enabled.

      

      

    Duration -> (integer)

      

      The duration of the Maintenance Window in hours.

      

      

    Cutoff -> (integer)

      

      The number of hours before the end of the Maintenance Window that Systems Manager stops scheduling new tasks for execution.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

