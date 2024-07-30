# README

## "import" script and example output

This repo contains the latest version of the local Gitlab->Github Action Import script: **import**

The **ComputeAorta** directory - and all its contents - represent output from an example **import** run using the following settings:

GITLAB (SOURCE) NAMESPACE / GROUP: **ComputeAorta**

GITLAB (SOURCE) REPO: **ca-llvm**

GITHUB (TARGET) REPO: **alan-forbes-cp/import_target**

The **import** script uses the **gh** (Github CLI) command and its **actions-importer** extension. Output of the following 4 actions-importer functions used are shown in sub-directories under the **ComputeAorta** directory:
1. audit
2. forecast
3. dry-run
4. migrate

These sub-directories are created by a single **import** run. Taken in the above order, they represent a typical action **import** workflow.

**audit** and **forecast** operate at **ComputeAorta** (source group) level. **dry-run** operates at **ca-llvm** (source repo) level. **migrate** operates at **ca-llvm**/**import_target** (source/target repo) level.

The **_command.out** files in the **ComputeAorta** directory contain the actual console output for each actions-importer operation and are included for completeness. You may need to "cat" these files at a console to get readable output.

Browsing each of the sub-directories under **ComputeAorta** should provide a flavour of the typical output for each of the actions-importer functions. In particular, note the following files from the audit, forecast and dry-run phases:

[ComputeAorta audit summary](https://github.com/alan-forbes-cp/import/blob/master/ComputeAorta/audit/audit_summary.md)

[ComputeAorta forecast report](https://github.com/alan-forbes-cp/import/blob/master/ComputeAorta/forecast/forecast_report.md)

[Dry-run generated ca-llvm Github action workflow .yml file](https://github.com/alan-forbes-cp/import/blob/master/ComputeAorta/dry-run/ComputeAorta/ca-llvm/.github/workflows/ca-llvm.yml)

The final migrate phase results in a PR being created in the target Github repo. For the **import** run used to populate the **ComputeAorta** sub-directories, the corresponding [PR can be found here](https://github.com/alan-forbes-cp/import_target/pull/1). Note that the file proposed for merging is the same .yml file as in the above-mentioned dry-run phase.

## "import" script set-up and configuration

TBD
