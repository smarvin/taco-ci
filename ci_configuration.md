---
title: CI Pipeline configuration
keywords: CI pipeline
sidebar: cip_sidebar
summary: "Configure your GitHub repo to automate testing for your Tableau connector."
permalink: ci_configuration.html
folder: ci-pipeline
---

You can make changes to your repository locally or in the GitHub UI. To make your changes locally, [clone](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository-from-github/cloning-a-repository) this repository to your device.

## Step 1: Add your resources
Add each resource listed below to its associated folder, where `<connector_folder>` is the name of your connector.

| Resource      | Directory |
| ----------- | ----------- |
| TACO file      | `taco/<connector_folder>/connector`       |
| Driver file   | `taco/<connector_folder>/driver/<os>`        |
| Setup script | `taco/<connector_folder>/driver/<os>` |
| Driver dependency files  | `taco/<connector_folder>/driver/<os>`  |
| Test configuration files  |  `taco/<connector_folder>/tdvt/config` |
| Calcs and staples tables  | `taco/<connector_folder>/tdvt/tds`  |
| Password files  | `taco/<connector_folder>/tdvt/password`  |
| (optional) Docker DB file  | `taco/<connector_folder>/docker`  |
| (optional) Docker setup script | `taco/<connector_folder>/docker`  |

## Step 2: Edit your configuration file

1. Open the `ci-default.json` file.
2. Edit the following key-value pairs to reflect your resources:

   | Key | Value |
   | --- | ------ |
   | `connector-file-path`   | Path to your TACO file |
   |`driver-file-path`  | Path to your driver file |
   | `setup-script-file-path` | Path to your setup script file |
   | `driver-dependency-files-path` | Path to your dependency files |
   | `connector-name` | Name of the your connector |
   | `test-suite-name` | Test suite name |
   | `test-config-files-path` | Path to your configuration file |
   | `tds-files-path` | Path to your TDS files  |
   | `password-files-path` | Path to your password files (need to explain) |
   | `file-path` | Path to your Docker DB |
   | `setup-script-file-path` |Path to your Docker setup script  |
   | `result-receiver` | Email addresses to send test results |

3. Save the file as `ci.json`.
4. Repeat for any other connector.

To see an example of the finished configuration file, see the <a href="#config_file">example cs.json</a> file.

## Step 3: Get your changes in the repo

If you are making changes locally, [commit](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/committing-and-reviewing-changes-to-your-project) and [push](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/pushing-changes-to-github) your changes to GitHub.

If you are making changes in the GitHub UI, add a description of your changes in the **Commit changes** area and click the **Commit changes** button.

Once you have finished with the configuration tasks, you can [start an automated test](ci_test.html).
