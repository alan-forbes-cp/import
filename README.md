# README

This repo contains the latest version of the local Gitlab->Github Action Import bash script: **import**. The following sections contain details of configuration and example usage.

## "import" script: environment set-up and configuration

### Environment

Any linux-flavour host with access to Gitlab and Github and running docker is suitable as an "import server"

The following tools should be installed:
- **docker**: (see relevant docs for this install)
- **gh** (Github command-line tool): e.g. for ubuntu "$ apt install gh"
- **gh actions-importer** extension:  "$ gh extension install github/gh-actions-importer"

The following source-side and target-side Git personal access tokens (PAT) should also be generated prior to configuring the actions-importer:
- Gitlab personal access token: with **read_api** scope only
- Github personal access token (classic): with **workflow** scope only

These should be generated and saved securely.

### Configuration

The actions-importer should be pre-configured with the command: "$ gh actions-importer configure"

You will be asked to enter configuration details for:
- provider: gitlab
- Github PAT: (as generated above)
- Github URL: https://github.com
- Gitlab PAT: (as generated above)
- Gitlab URL: https://git.office.codeplay.com

Note that the actions-importer configure command will create the file: **.env_local** in your CWD. All gh actions-importer commands requiring these configuration details (and the **import** wrapper script itself) should be run from this work directory.

Once configured, update the actions-importer to the latest version with: "$ gh actions-importer update"

At this point you are ready to run the full suite of gh actions-import workflow commands: audit/forecast/dry-run/migrate and the **import** wrapper script.

Note that the migrate function needs a non-empty repo on the Github (target) side - so for newly created target repos at least e.g. a README or similar is required.

## "import" script: runtime and example output

Run **import** with: "$ import"

The **ComputeAorta** directory in this repo - and all its contents - represent output from an example **import** run using the following settings:

GITLAB (SOURCE) NAMESPACE / GROUP: **ComputeAorta**

GITLAB (SOURCE) REPO: **ca-llvm**

GITHUB (TARGET) REPO: **alan-forbes-cp/import_target**

These can be tailored in the **import** script as required for individual circumstances.

The **import** script uses the **gh** (Github CLI) command and its **actions-importer** extension. Output of the following 4 actions-importer functions used are shown in sub-directories under the **ComputeAorta** directory:
1. audit (aka plan)
2. forecast
3. dry-run
4. migrate

These sub-directories are created by a single **import** run. Taken in the above order, they represent a typical action **import** workflow.

**audit** and **forecast** operate at **ComputeAorta** (source group) level. **dry-run** operates at **ca-llvm** (source repo) level. **migrate** operates at **ca-llvm**/**import_target** (source/target repo) level.

The **_command.out** files in the **ComputeAorta** directory contain the actual console output for each actions-importer operation and are included for completeness. You may need to "cat" these files at a console to get readable output.

Browsing each of the sub-directories under **ComputeAorta** should provide a flavour of the typical output for each of the actions-importer functions. In particular, note the following files from the audit (or plan), forecast and dry-run phases:

[ComputeAorta audit summary](https://github.com/alan-forbes-cp/import/blob/master/ComputeAorta/audit/audit_summary.md)

[ComputeAorta forecast report](https://github.com/alan-forbes-cp/import/blob/master/ComputeAorta/forecast/forecast_report.md)

[Dry-run generated ca-llvm Github action workflow .yml file](https://github.com/alan-forbes-cp/import/blob/master/ComputeAorta/dry-run/ComputeAorta/ca-llvm/.github/workflows/ca-llvm.yml)

The final migrate phase results in a PR being created in the target Github repo. For the **import** run used to populate the **ComputeAorta** sub-directories, the corresponding [PR can be found here](https://github.com/alan-forbes-cp/import_target/pull/1). Note that the file proposed for merging is the same .yml file as in the above-mentioned dry-run phase.

There is a useful workflow overview here: https://www.youtube.com/watch?v=3t5ywu0_qk4
