# aci-registry-rs

This crate provides programmatic interfaces to represent the types of Device Classes, Device Subclasses, Device Vendors, and Device Products. for the ACI Specification.

Additionally, this crate provides information about device classes, vendors, and well-known subclasses

## Features

The following crate features are provided:
* `fixed-repr`: Causes each well-known subclass enum, [`DeviceClass`], [`DeviceVendor`], [`SubclassId`], and [`ProductId`] to all be represented as a native-endian `u16`,
 which is suitable for encoding/decoding for transport, specifically as the Device Class/Subclass and Device Vendor/Product fields
* `extended-info`: Provides information that is generally unneeded by drivers or firmware for ACI Devices for well-known subclass enums, [`DeviceClass`], and [`DeviceVendor`]

## Use
There are three primary uses for this crate:
* The development of firmware for ACI Compliant Devices, or low-level components of an ACI Host
* The development of drivers for ACI Complaint Devices, or generic portions of ACI Host System Software
* The development of tools which provide information about ACI devices

To Faciliate the first two use cases, the crate is `no_std` and does not require the `alloc` crate. This allows it to be used in bare metal freestanding systems without issue

## Other Subclasses/Product Ids

Presently, only the lists of devices, vendors, and well-known subclasses, maintained in the Clever-ISA project source copy of the [ACI-Registry](https://github.com/Clever-ISA/ACI-Registry)
 are exposed through strongly typed enumerations.

In the future, subclasses of non-well known classes, and product ids may be listed

## Out of Date Registries

The registry associated with this crate is kept in sync by periodic updates within a few hours of modifications to the registry.
If newer registriations are not available, you may need to use a later version of this crate.

It is considered a semver patch to update the copy of the registry associated with a version of this crate.


## License

Copyright (C) 2024 Connor Horman

This project is released under the terms of the Apache 2.0 or MIT License, at your option. 

Unless you state otherwise, any contribution intentionally submitted by you to this repository will be released under the above dual license. 