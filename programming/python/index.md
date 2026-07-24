---
title: Introduction - Dynamsoft Barcode Reader Python Edition
keywords: python, documentation
description: Overview of DBR Python Edition, including feature highlights, system requirements, and links to the user guide, API reference, and migration guides.
needAutoGenerateSidebar: false
---

# Introduction to Dynamsoft Barcode Reader Python Edition

Dynamsoft Barcode Reader (DBR) SDK Python Edition is a barcode reading tool designed specifically for python developers.

Leveraging the efficiency and flexibility of the python language, DBR Python Edition provides rich APIs for developers to easily integrate barcode reading functionality into your python applications. Please take a look at [API Reference]({{ site.dbr_python_api }}) to see details.

As one of the functional products of the Dynamsoft Capture Vision (DCV) framework, DBR is also designed to seamlessly integrate with other DCV components and provide developers with a comprehensive set of image processing tools, which cover image capturing, content understanding, result parsing, and interactive workflow. If you are building such a capturing and processing solution, take a look at [Introduction to Dynamsoft Capture Vision]({{ site.dcvb_architecture }}).

Furthermore, DBR provides a powerful parameter system in order to cope with various scenarios. Read [Parameters]({{ site.dcvb_parameters }}file/index.html) for details.

## Getting Started with DBR Python Edition

If you are new to Dynamsoft Barcode Reader Python Edition, follow the [`User Guide`]({{ site.dbr_python }}user-guide.html) to build your first barcode reading application. Please note that the system requirements is as below:

## System Requirements

### Supported Platforms

**Windows**
- Supported Versions: Windows 8 and higher, or Windows Server 2012 and higher
- Architectures: x64

**Linux**
- **x64**
	- Supported Distributions: Ubuntu 16.04+ LTS, Debian 8+, CentOS 7+
	- Dependencies: glibc 2.17
- **ARM64**
	- Supported Distributions: Ubuntu 18.04+ LTS, Debian 10+, CentOS/RHEL 8+
	- Dependencies: glibc 2.27

**macOS**
- Supported Versions: macOS 12 (Monterey) and higher
- Architectures: universal (x64, Apple Silicon)

### Supported Python Versions

- Python 3.14
- Python 3.13
- Python 3.12
- Python 3.11
- Python 3.10
- Python 3.9
- Python 3.8
- Python 3.7 (for versions below DBR 9.6.40.2)
- Python 3.6 (for versions below DBR 9.6.40.2)
- Python 3.5 (for versions below DBR 7.5)
- Python 2.7 (for versions below DBR 7.2.2.3)

### Embedded Devices

For embedded or ARM-based platforms, we recommend using a device with performance equivalent to or better than a Raspberry Pi 4 Model B (4 GB RAM). Minimum recommended specs:

- Quad-core ARM Cortex-A72 processor or equivalent
- 4 GB RAM
- Linux-based OS, such as Raspberry Pi OS or Ubuntu Server

> [!NOTE]
> Other architectures and operating systems, such as ESP32, MIPS, FreeRTOS, and Micrium uC/OS, are not supported.

## Migration Guides

If you are upgrading from a previous version of Dynamsoft Barcode Reader, please refer to the following guides:

- [Migrate from v10.x to v11.x]({{ site.dbr_python }}migrate-from-v10/) - For users upgrading from version 10.x
- [Migrate from v9.x to v11.x]({{ site.dbr_python }}migrate-from-v9/) - For users upgrading from version 9.x

## API Reference

For an overview of the APIs, see the [API Reference]({{ site.dbr_python_api }}).

## Release Notes

For a peek of DBR Python Edition history, check the [Release Notes]({{ site.dbr_python_release_notes }}).

## License Subscription

To develop and run your application with Dynamsoft Barcode Reader SDK, you need an active license key:
* <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=docs&product=dbr&package=python" target="_blank">Request a 30-day free trial license</a>

## Thread Safety

The SDK supports multi-threaded applications, but individual SDK instances are not thread-safe.  
For concurrent processing, create a separate instance for each thread.

## Contact Us

<a href="https://www.dynamsoft.com/company/customer-service/#contact" target="_blank">Feel free to contact us if you have any questions.</a>