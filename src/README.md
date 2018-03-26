# Wave Local Data Dictionary (LDD)

The Wave dictionary contains classes that describe the composition of multidimensional wave data consisting of Array (and Array subclass) data objects.

Steward: PPI

## Classes

### Axis_Values
The Axis_Values class describes the values which are associated with the elements along an axis of a observation data array.

Attribute    | Min Occur. | Max Occur.
------------ | ---------- | -----------
[Local_Internal_Reference](#Local_Internal_Reference)  | 1 | 1
[axis_number](#axis_number)  | 1          | 1

### Face_Values
The Face_Values class describes the values which are associated with the elements on the face of a observation data array.

Attribute    | Min Occur. | Max Occur.
------------ | ---------- | -----------
[Local_Internal_Reference](#Local_Internal_Reference)  | 1 | 1
[Face_Plane](#Face_Plane)   | 1          | 1

### Face_Plane
The Face_Plane class describes a plane which is defined by two axes.

Attribute    | Min Occur. | Max Occur.
------------ | ---------- | -----------
[face_axis](#face_axis)    | 2          | 2

### Local_Internal_Reference
The Local_Internal_Reference class is used to cross-reference other classes or objects within the product.

Attribute    | Min Occur. | Max Occur.
------------ | ---------- | -----------
pds.local_identifier_reference | 1 | 1
[local_reference_type](#local_reference_type)      | 1 | 1
pds.comment  | 0          | 1

### Wave_Observation
The Wave_Observation describes the data of a observation and the values which are associated with the elements along an axis or on the face of a observation data array.

Attribute    | Min Occur. | Max Occur.
------------ | ---------- | -----------
pds.name     | 1          | 1
pds.local_identifier | 0  | 1
pds.description | 1       | 1
[Primary_Values](#Primary_Values) | 1        | 1
[Axis_Values](#Axis_Values)  | 0          | *
[Face_Values](#Face_Values)  | 0          | *

### Primary_Values
The Primary_Values class describes the values which are the primary observation data array.

Attribute    | Min Occur. | Max Occur.
------------ | ---------- | -----------
[Local_Internal_Reference](#Local_Internal_Reference) | 1 | 1

## Attributes

### axis_number
The index of the axis. The first axis is numbered as 1.

Type: ASCII_Integer

### face_axis
The axis number that defines one axis of a face plane.

Type: ASCII_Integer

### local_reference_type
The local_reference_type attribute provides the name of an association between an entity identified by a local_identifier_reference and another corresponding entity identified by a local_identifier

Type: ASCII_Short_String_Collapsed

Allowed Values:

Name                                    | Description
--------------------------------------- | ----------------------------
wave_observation_to_observation_values  | A reference to the array containing the primary observation data.
wave_observation_to_axis_values         | A reference to the array containing the data values for an axis of primary observation data.
wave_observation_to_face_values         | A reference to the array containing the data values for a face of primary observation data.
