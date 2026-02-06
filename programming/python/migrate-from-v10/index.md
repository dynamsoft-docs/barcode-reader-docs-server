---
title: Migrate from v10.x to v11.x - Dynamsoft Barcode Reader SDK Python Edition
keywords: python, upgrade, migrate, v10, v11
description: This page introduces how to migrate Dynamsoft Barcode Reader SDK Python Edition from version 10.x to 11.x
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

# Migrate from 10.x to 11.x

Version 11.x is fully API-compatible with version 10.x. Most applications can upgrade by simply updating the package without code changes. Follow these steps to complete the migration.

## Update the License Key

You may need to update your license key before upgrading to version 11.x.

- **30-Day Free Trial License**: Visit the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=docs){:target="_blank"} page to obtain a free license for evaluation.
- **Annual Online Full License**: Your license will continue to work with the new SDK version. Go to <a href="https://www.dynamsoft.com/customer/license/fullLicense" target="_blank">Customer Portal</a> to get your license key.
- **Perpetual License**: Please contact our [sales team](https://www.dynamsoft.com/contact/){:target="_blank"} to update your license.

## Update the Package

Run the following command to upgrade to the latest version:

```bash
pip install dynamsoft-barcode-reader-bundle --upgrade
```

## Upgrade Template Files

The template file format has changed. Templates created for version 10.x may not be fully compatible with version 11.x. Use the <a href="https://www.dynamsoft.com/tools/template-upgrade/" target="_blank">Template Upgrade Tool</a> to convert your existing templates to the new format.
