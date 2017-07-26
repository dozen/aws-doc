[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint delete-segment:


**************
delete-segment
**************



===========
Description
===========

Deletes a segment.

========
Synopsis
========

::

    delete-segment
  --application-id <value>
  --segment-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--segment-id`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SegmentResponse -> (structure)

  Segment definition.

  ApplicationId -> (string)

    The ID of the application to which the segment applies.

    

  CreationDate -> (string)

    The date the segment was created in ISO 8601 format.

    

  Dimensions -> (structure)

    The segment dimensions attributes.

    Attributes -> (map)

      Custom segment attributes.

      key -> (string)

        

        

      value -> (structure)

        Custom attibute dimension

        AttributeType -> (string)

          The type of dimension: INCLUSIVE - Endpoints that match the criteria are included in the segment. EXCLUSIVE - Endpoints that match the criteria are excluded from the segment.

          

        Values -> (list)

          The criteria values for the segment dimension. Endpoints with matching attribute values are included or excluded from the segment, depending on the setting for Type.

          (string)

            

            

          

        

      

    Behavior -> (structure)

      The segment behaviors attributes.

      Recency -> (structure)

        The recency of use.

        Duration -> (string)

          The length of time during which users have been active or inactive with your app. Valid values: HR_24, DAY_7, DAY_14, DAY_30

          

        RecencyType -> (string)

          The recency dimension type: ACTIVE - Users who have used your app within the specified duration are included in the segment. INACTIVE - Users who have not used your app within the specified duration are included in the segment.

          

        

      

    Demographic -> (structure)

      The segment demographics attributes.

      AppVersion -> (structure)

        The app version criteria for the segment.

        DimensionType -> (string)

          The type of dimension: INCLUSIVE - Endpoints that match the criteria are included in the segment. EXCLUSIVE - Endpoints that match the criteria are excluded from the segment.

          

        Values -> (list)

          The criteria values for the segment dimension. Endpoints with matching attribute values are included or excluded from the segment, depending on the setting for Type.

          (string)

            

            

          

        

      Channel -> (structure)

        The channel criteria for the segment.

        DimensionType -> (string)

          The type of dimension: INCLUSIVE - Endpoints that match the criteria are included in the segment. EXCLUSIVE - Endpoints that match the criteria are excluded from the segment.

          

        Values -> (list)

          The criteria values for the segment dimension. Endpoints with matching attribute values are included or excluded from the segment, depending on the setting for Type.

          (string)

            

            

          

        

      DeviceType -> (structure)

        The device type criteria for the segment.

        DimensionType -> (string)

          The type of dimension: INCLUSIVE - Endpoints that match the criteria are included in the segment. EXCLUSIVE - Endpoints that match the criteria are excluded from the segment.

          

        Values -> (list)

          The criteria values for the segment dimension. Endpoints with matching attribute values are included or excluded from the segment, depending on the setting for Type.

          (string)

            

            

          

        

      Make -> (structure)

        The device make criteria for the segment.

        DimensionType -> (string)

          The type of dimension: INCLUSIVE - Endpoints that match the criteria are included in the segment. EXCLUSIVE - Endpoints that match the criteria are excluded from the segment.

          

        Values -> (list)

          The criteria values for the segment dimension. Endpoints with matching attribute values are included or excluded from the segment, depending on the setting for Type.

          (string)

            

            

          

        

      Model -> (structure)

        The device model criteria for the segment.

        DimensionType -> (string)

          The type of dimension: INCLUSIVE - Endpoints that match the criteria are included in the segment. EXCLUSIVE - Endpoints that match the criteria are excluded from the segment.

          

        Values -> (list)

          The criteria values for the segment dimension. Endpoints with matching attribute values are included or excluded from the segment, depending on the setting for Type.

          (string)

            

            

          

        

      Platform -> (structure)

        The device platform criteria for the segment.

        DimensionType -> (string)

          The type of dimension: INCLUSIVE - Endpoints that match the criteria are included in the segment. EXCLUSIVE - Endpoints that match the criteria are excluded from the segment.

          

        Values -> (list)

          The criteria values for the segment dimension. Endpoints with matching attribute values are included or excluded from the segment, depending on the setting for Type.

          (string)

            

            

          

        

      

    Location -> (structure)

      The segment location attributes.

      Country -> (structure)

        The country filter according to ISO 3166-1 Alpha-2 codes.

        DimensionType -> (string)

          The type of dimension: INCLUSIVE - Endpoints that match the criteria are included in the segment. EXCLUSIVE - Endpoints that match the criteria are excluded from the segment.

          

        Values -> (list)

          The criteria values for the segment dimension. Endpoints with matching attribute values are included or excluded from the segment, depending on the setting for Type.

          (string)

            

            

          

        

      

    UserAttributes -> (map)

      Custom segment user attributes.

      key -> (string)

        

        

      value -> (structure)

        Custom attibute dimension

        AttributeType -> (string)

          The type of dimension: INCLUSIVE - Endpoints that match the criteria are included in the segment. EXCLUSIVE - Endpoints that match the criteria are excluded from the segment.

          

        Values -> (list)

          The criteria values for the segment dimension. Endpoints with matching attribute values are included or excluded from the segment, depending on the setting for Type.

          (string)

            

            

          

        

      

    

  Id -> (string)

    The unique segment ID.

    

  ImportDefinition -> (structure)

    The import job settings.

    ChannelCounts -> (map)

      Channel type counts

      key -> (string)

        

        

      value -> (integer)

        

        

      

    ExternalId -> (string)

      A unique, custom ID assigned to the IAM role that restricts who can assume the role.

      

    Format -> (string)

      The format of the endpoint files that were imported to create this segment. Valid values: CSV, JSON

      

    RoleArn -> (string)

      The Amazon Resource Name (ARN) of an IAM role that grants Amazon Pinpoint access to the endpoints in Amazon S3.

      

    S3Url -> (string)

      A URL that points to the Amazon S3 location from which the endpoints for this segment were imported.

      

    Size -> (integer)

      The number of endpoints that were successfully imported to create this segment.

      

    

  LastModifiedDate -> (string)

    The date the segment was last updated in ISO 8601 format.

    

  Name -> (string)

    The name of segment

    

  SegmentType -> (string)

    The segment type: DIMENSIONAL - A dynamic segment built from selection criteria based on endpoint data reported by your app. You create this type of segment by using the segment builder in the Amazon Pinpoint console or by making a POST request to the segments resource. IMPORT - A static segment built from an imported set of endpoint definitions. You create this type of segment by importing a segment in the Amazon Pinpoint console or by making a POST request to the jobs/import resource.

    

  Version -> (integer)

    The segment version number.

    

  

