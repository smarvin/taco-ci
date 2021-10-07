---
title: Configuration
keywords: CI pipeline
sidebar: cip_sidebar
summary: "Configure your GitHub repo to automate testing for your Tableau connector."
permalink: ci_configuration.html
folder: ci-pipeline
---

You can configure your repository locally or in the GitHub UI. To make your changes locally, [clone](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository-from-github/cloning-a-repository) this repository to your device.

## Step 1: Add your resources
Add each of the following resources to its associated folder, where `<connector_folder>` is the name of your connector.

| Resource      | Directory |
| ----------- | ----------- |
| TACO file      | `taco/<connector_folder>/connector`       |
| Driver file   | `taco/<connector_folder>/driver/<os>`        |
| Setup script | `taco/<connector_folder>/driver/<os>` |
| Driver dependency files  | `taco/<connector_folder>/driver/<os>`  |
| Test configuration files  |  `taco/<connector_folder>/tdvt/config` |
| Calcs and staples tables  | `taco/<connector_folder>/tdvt/tds`  |
| (optional) Password files  | `taco/<connector_folder>/tdvt/password`  |

## Step 2: Edit your configuration file

The configuration file for the Github Action workflow is `ci.json`.

1. Open the `ci.json` file for your connector.
2. Edit the following key-value pairs to reflect your resources:

   | Key | Value |
   | --- | ------ |
   | `connector-file-path`   | Path to your TACO file |
   | `driver-file-path`  | Path to your driver file |
   | `setup-script-file-path` | Path to your setup script file |
   | `driver-dependency-files-path` | Path to your dependency files |
   | `connector-name` | Name of your connector |
   | `test-suite-name` | Test suite name |
   | `test-config-files-path` | Path to your configuration file |
   | `tds-files-path` | Path to your TDS files  |
   | `password-files-path` | Path to your tdvt password files |
   | `result-receiver` | Email addresses to send test results |

3. Commit the file changes, and create a new release from Github UI or push a new git tag to the repository to trigger the Github Action workflow to validate.

To see an example of the finished configuration file, see the <a href="#config_file">example cs.json</a> file.

After you have finished with the configuration tasks, you can [start an automated test](ci_test.html).
