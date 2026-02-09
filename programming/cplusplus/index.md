---
title: Introduction - Dynamsoft Barcode Reader C++ Edition
keywords: c++, cplusplus, documentation
description: This page introduces the C++ edition of Dynamsoft Barcode Reader
needAutoGenerateSidebar: false
---

# Dynamsoft Barcode Reader Documentation for C++ Edition

Dynamsoft Barcode Reader (DBR) SDK C++ Edition is a barcode reading tool designed specifically for C++ developers.

Leveraging the efficiency and flexibility of the C++ language, DBR C++ Edition provides rich APIs for developers to easily integrate barcode reading functionality into your c++ applications. Please take a look at [API Reference]({{ site.dbr_cpp_api }}index.html) to see details.

In addition, DBR C++ Edition provides cross-platform support, running on multiple operating systems such as Windows, Linux, and Mac, to meet the needs of different development environments

As one of the functional products of the Dynamsoft Capture Vision (DCV) framework, DBR is also designed to seamlessly integrate with other DCV components and provide developers with a comprehensive set of image processing tools, which cover image capturing, content understanding, result parsing, and interactive workflow. If you are building such a capturing and processing solution, take a look at [Introduction to Dynamsoft Capture Vision]({{ site.dcvb_architecture }}).

Furthermore, DBR provides a powerful parameter system in order to cope with various scenarios. Read [Parameters]({{ site.dbr_parameters }}structure-and-interfaces-of-parameters.html) for details.

## Getting Started with DBR C++ Edition

If you are new to Dynamsoft Barcode Reader C++ Edition, follow the [`User Guide`]({{site.dbr_cpp}}user-guide.html) to build your first barcode reading application. Please note that the system requirements is as below:

### System Requirements

- Windows:
  - Supported Versions: Windows 8 and higher, or Windows Server 2012 and higher
  - Architecture: x64 and x86
  - Development Environment: Visual Studio 2012 or higher.

- Linux:
  - Supported Distributions: Ubuntu 14.04.4+ LTS, Debian 8+, CentOS 7+
  - Architectures: x64, ARM 64-bit, ARM 32-bit (for versions below 9.6.40.2)
  - Minimum GLIBC Version: GLIBC_2.18 or higher
  - Compiler: G++ 5.4 or higher

- macOS (Universal) 12+ (not included in the trial package, contact us to get the SDK)

- For Embedded Devices:
For embedded or ARM-based platforms, we recommend using a device with performance equivalent to or better than a Raspberry Pi 4 Model B (4GB RAM). Minimum recommended specs:
  - Quad-core ARM Cortex-A72 processor (or equivalent)
  - 4 GB RAM
  - Linux-based OS (e.g., Raspberry Pi OS, Ubuntu Server)

> [!NOTE]
> Other architectures and operating systems, such as ESP32, MIPS, FreeRTOS, and Micrium uC/OS, are not supported.

## Migration Guides

If you are upgrading from a previous version of Dynamsoft Barcode Reader, please refer to the following guides:

- [Migrate from v10.x to v11.x]({{ site.dbr_cpp }}migrate-from-v10/) - For users upgrading from version 10.x
- [Migrate from v9.x to v11.x]({{ site.dbr_cpp }}migrate-from-v9/) - For users upgrading from version 9.x

## API Reference

For an overview of the APIs, see the [API Reference]({{ site.dbr_cpp_api }}index.html).

## Release Notes

For a peek of DBR C++ Edition history, check the [Release Notes]({{ site.dbr_cpp_release_notes }}).

## License Subscription

To develop and run your application with Dynamsoft Barcode Reader SDK, you need an active license key:
* <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=docs&product=dbr&package=c_cpp" target="_blank">Request a 30-day free trial license</a>

## Contact Us

<a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">Feel free to contact us if you have any questions.</a>