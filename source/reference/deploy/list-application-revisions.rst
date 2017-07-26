[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-application-revisions:


**************************
list-application-revisions
**************************



===========
Description
===========



Lists information about revisions for an application.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/ListApplicationRevisions>`_


``list-application-revisions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``revisions``


========
Synopsis
========

::

    list-application-revisions
  --application-name <value>
  [--sort-by <value>]
  [--sort-order <value>]
  [--s-3-bucket <value>]
  [--s-3-key-prefix <value>]
  [--deployed <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--sort-by`` (string)


  The column name to use to sort the list results:

   

   
  * registerTime: Sort by the time the revisions were registered with AWS CodeDeploy. 
   
  * firstUsedTime: Sort by the time the revisions were first used in a deployment. 
   
  * lastUsedTime: Sort by the time the revisions were last used in a deployment. 
   

   

  If not specified or set to null, the results will be returned in an arbitrary order.

  

  Possible values:

  
  *   ``registerTime``

  
  *   ``firstUsedTime``

  
  *   ``lastUsedTime``

  

  

``--sort-order`` (string)


  The order in which to sort the list results:

   

   
  * ascending: ascending order. 
   
  * descending: descending order. 
   

   

  If not specified, the results will be sorted in ascending order.

   

  If set to null, the results will be sorted in an arbitrary order.

  

  Possible values:

  
  *   ``ascending``

  
  *   ``descending``

  

  

``--s-3-bucket`` (string)


  An Amazon S3 bucket name to limit the search for revisions.

   

  If set to null, all of the user's buckets will be searched.

  

``--s-3-key-prefix`` (string)


  A key prefix for the set of Amazon S3 objects to limit the search for revisions.

  

``--deployed`` (string)


  Whether to list revisions based on whether the revision is the target revision of an deployment group:

   

   
  * include: List revisions that are target revisions of a deployment group. 
   
  * exclude: Do not list revisions that are target revisions of a deployment group. 
   
  * ignore: List all revisions. 
   

  

  Possible values:

  
  *   ``include``

  
  *   ``exclude``

  
  *   ``ignore``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about application revisions**

This example displays information about all application revisions that are associated with the specified application.

Command::

  aws deploy list-application-revisions --application-name WordPress_App --s-3-bucket CodeDeployDemoBucket --deployed exclude --s-3-key-prefix WordPress_ --sort-by lastUsedTime --sort-order descending

Output::

  {
      "revisions": [
          {
              "revisionType": "S3",
			  "s3Location": {
                "version": "uTecLusvCB_JqHFXtfUcyfV8bEXAMPLE",
                "bucket": "CodeDeployDemoBucket",
                "key": "WordPress_App.zip",
				"bundleType": "zip"
		      }
          },
          {
              "revisionType": "S3",
			  "s3Location": {
                "version": "tMk.UxgDpMEVb7V187ZM6wVAWEXAMPLE",
                "bucket": "CodeDeployDemoBucket",
                "key": "WordPress_App_2-0.zip",
				"bundleType": "zip"
	          }
          }
      ]
  }


======
Output
======

revisions -> (list)

  

  A list of locations that contain the matching revisions.

  

  (structure)

    

    Information about the location of an application revision.

    

    revisionType -> (string)

      

      The type of application revision:

       

       
      * S3: An application revision stored in Amazon S3. 
       
      * GitHub: An application revision stored in GitHub. 
       

      

      

    s3Location -> (structure)

      

      Information about the location of application artifacts stored in Amazon S3. 

      

      bucket -> (string)

        

        The name of the Amazon S3 bucket where the application revision is stored.

        

        

      key -> (string)

        

        The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

        

        

      bundleType -> (string)

        

        The file type of the application revision. Must be one of the following:

         

         
        * tar: A tar archive file. 
         
        * tgz: A compressed tar archive file. 
         
        * zip: A zip archive file. 
         

        

        

      version -> (string)

        

        A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

         

        If the version is not specified, the system will use the most recent version by default.

        

        

      eTag -> (string)

        

        The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

         

        If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

        

        

      

    gitHubLocation -> (structure)

      

      Information about the location of application artifacts stored in GitHub.

      

      repository -> (string)

        

        The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

         

        Specified as account/repository.

        

        

      commitId -> (string)

        

        The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

        

        

      

    

  

nextToken -> (string)

  

  If a large amount of information is returned, an identifier will also be returned. It can be used in a subsequent list application revisions call to return the next set of application revisions in the list.

  

  

