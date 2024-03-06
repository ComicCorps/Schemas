# Schemas

## What is it?

`Metadata.xml` is an attempt to create a new schema for digital comic books that fixes the issues I have with the existing `ComicInfo.xml` schema.

## Why?

The `ComicInfo.xml` schema originates from the ComicRack application, which is not developed anymore, there is an attempt to update it ([anansi-project/comicinfo](https://github.com/anansi-project/comicinfo)), but it still lacks support for certain features.

By creating a new schema incompatable changes can be made, such as:

- Additional fields
- Better data types, instead of comma-seperated strings for everything lists are nested
- Linking of IDs to datasources for better data collection.

## Files

- `/drafts`: Location of current draft.
- `/schemas`: Location of versioned schema, and location of external schemas.

_Each version of a schema is stored in a seperate directory_

## External schemas

The other schemas supported by ComicCorps are:

- [MetronInfo v1.0 - draft](https://github.com/Metron-Project/metroninfo/raw/23fe266020d30669de55460c87b190b41c25e549/drafts/v1.0/MetronInfo.xsd)
- [ComicInfo v2.0](https://github.com/anansi-project/comicinfo/raw/75d00db57927bf6776717fc1060cb7f594186cb3/schema/v2.0/ComicInfo.xsd)

_The ComicInfo schema has been slightly adjusted to ignore field ordering_

```diff
<xs:complexType name="ComicInfo">
-  <xs:sequence>
+  <xs:all>
```