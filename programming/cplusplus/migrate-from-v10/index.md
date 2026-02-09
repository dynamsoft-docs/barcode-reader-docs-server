---
title: Migrate from v10.x to v11.x - Dynamsoft Barcode Reader SDK C++ Edition
keywords: c++, cplusplus, upgrade, migrate, v10, v11
description: This page introduces how to migrate Dynamsoft Barcode Reader SDK C++ Edition from version 10.x to 11.x
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# Migrate from 10.x to 11.x

Version 11.x is fully API-compatible with version 10.x. Most applications can upgrade by simply updating the SDK files without code changes. Follow these steps to complete the migration.

## Update the License Key

You may need to update your license key before upgrading to version 11.x.

- **30-Day Free Trial License**: Visit the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs){:target="_blank"} page to obtain a free license for evaluation.
- **Annual Online Full License**: Your license will continue to work with the new SDK version. Go to <a href="https://www.dynamsoft.com/customer/license/fullLicense" target="_blank">Customer Portal</a> to get your license key.
- **Perpetual License**: Please contact our [sales team](https://www.dynamsoft.com/contact/){:target="_blank"} to update your license.

## Update SDK Files

<a href="https://www.dynamsoft.com/barcode-reader/downloads/" target="_blank">Download the latest SDK package</a> and update the header and library files. Note the following changes:

- **Directory Structure**: The `Distributables` directory has been renamed to `Dist`.
- **vcomp140.dll Removed**: This DLL is no longer included. If your application requires OpenMP support, ensure the [Visual C++ Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist){:target="_blank"} is installed on the target system.

## Upgrade Template Files

The template file format has changed. Templates created for version 10.x may not be fully compatible with version 11.x. Use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">Template Upgrade Tool</a> to convert your existing templates to the new format.

## Rebuild the Project

After updating the SDK files, clean and rebuild your project to ensure all dependencies are properly linked.


