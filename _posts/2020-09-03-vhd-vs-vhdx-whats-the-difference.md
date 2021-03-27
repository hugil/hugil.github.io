---
title: "VHD vs VHDX, what's the difference?"
categories:
  - Virtualization
tags:
  - hyper-v
header:
  teaser: assets/images/vhd-vs-vhdx-thumbnail.png
  og_image: assets/images/vhd-vs-vhdx-thumbnail.png
last_modified_at: 2021-03-23T15:12:19-04:00
---
These are the major differences:

-   **Compatibility:**  VHD is supported by 2008, 2008R2, 2012R2 and 2012 versions of Windows Server. But VHDX is supported by Windows Server 2012 and later versions only.
-   **Capacity:**  With the old VHD file format, the storage limit is restricted to 2TB; but with the new VHDX format, the maximum storage limit is 64TB.
-   **Logical Sectors:**  The new VHDX format supports 4KB logical sector size which is a nice performance boost. While VHD format file supports logical sector size of 512 bytes only.
-   **Data Protection:**  One more special feature about the new VHDX format is that the self-protection it provides against file corruption from unexpected IO failure (by tracking metadata) caused by issues like sudden power outage. It also provides larger blocks than VHD file for dynamic and differential disks with custom metadata features.
-   **Resizing:**  Live resizing is possible for VHDX files, whereas it is not possible for VHD files.
-   **Data Alignment and Trimming:**  VHD file format have issues with data alignment while VHDX file offers smooth data alignment. Also trimming feature is available only in VHDX file formats.
-   **Storage Types: :**  Now let’s look at different storage types with VHDX. Hyper-V allows you to create two primary hard disk storage types – fixed and dynamic. The great aspect about dynamic size is its requirement for minimum initial space. And the size expands proportionately as one uses the space. On other hand with the fixed storage type, the size for your storage is fixed. In terms of performance, fixed storage is efficient compared to the dynamic one.