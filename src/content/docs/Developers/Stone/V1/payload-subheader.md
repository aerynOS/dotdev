---
title: Payload's sub-header
lastUpdated: 2026-10-02T15:00:00Z
description: The content of Payload's sub-header
license: "CC-BY-SA-4.0"
copyright: "Copyright © 2025 aerynOS Developers"
---

Described below is the format of the 32-byte-long payload sub-header. This format is unique to v1.

<table>
  <tr>
    <th>Field</th>
    <th>Type</th>
    <th>Size (bytes)</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>stored_size</td>
    <td>uint</td>
    <td>8</td>
    <td>
        Compressed size, in bytes, of the records. If records are not compressed, stored_size is equal to plain_size.
    </td>
  </tr>
  <tr>
    <td>plain_size</td>
    <td>uint</td>
    <td>8</td>
    <td>Uncompressed size, in bytes, of records.</td>
  </tr>
  <tr>
    <td>checksum</td>
    <td>blob</td>
    <td>8</td>
    <td>Checksum of records, computed using <a href="https://xxhash.com">XXH3_64bits</a>.</td>
  </tr>
  <tr>
    <td>num_records</td>
    <td>uint</td>
    <td>4</td>
    <td>Number of records contained in the payload.</td>
  </tr>
  <tr>
    <td>version</td>
    <td>uint</td>
    <td>2</td>
    <td>Version of the payload data format. Unused.</td>
  </tr>
  <tr>
    <td>record_kind</td>
    <td>uint</td>
    <td>1</td>
    <td>Kind of records that the payload contains.</td>
  </tr>
  <tr>
    <td>compression</td>
    <td>uint</td>
    <td>1</td>
    <td>Compression algorithm used for the records.</td>
  </tr>
</table>

### record_kind

`record_kind` is an enum. The following table lists all possible values:

|Value|Name|
|---|---|
|1|[Meta](/developers/stone/v1/record/meta/)|
|2|[Content](/developers/stone/v1/record/content/)|
|3|[Layout](/developers/stone/v1/record/layout/)|
|4|[Index](/developers/stone/v1/record/indexs/)|
|5|[Attribute](/developers/stone/v1/record/attribute/)|

### compression
|Value|Name|
|---|---|
|1|Uncompressed|
|2|Zstd|
