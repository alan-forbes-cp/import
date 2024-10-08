# README: "import" script

This repo contains the latest version of the local Gitlab->Github Action Import bash script: **import**. The script is a wrapper around the Github **gh** actions-importer extension. (See: https://docs.github.com/en/actions/migrating-to-github-actions/using-github-actions-importer-to-automate-migrations/automating-migration-with-github-actions-importer). The following sections contain details of **import** configuration, example usage and "gotchas".

## Environment set-up and configuration

### Environment

Any linux-flavour host i. with access to Gitlab and Github and ii. running docker is suitable as an "import server".

The following tools should be installed:
- **docker**: (see relevant docs for this install).
- **gh** (Github command-line tool): e.g. for ubuntu: "$ apt install gh"
- **gh actions-importer** extension:  "$ gh extension install github/gh-actions-importer"

The following source-side and target-side Git personal access tokens (PAT) should also be generated prior to configuring the actions-importer:
- Gitlab personal access token: with **read_api** scope only.
- Github personal access token (classic): with **workflow** scope only.

These should be generated and saved securely. (See below for usage.)

### Configuration

The actions-importer should be pre-configured using the command: "$ gh actions-importer configure"

You will be asked to enter configuration details for:
- provider: **gitlab**
- Github PAT: (as generated above)
- Github URL: https://github.com
- Gitlab PAT: (as generated above)
- Gitlab URL: https://git.office.codeplay.com

Note that the actions-importer configure command will create the file: **.env_local** in your CWD. All gh actions-importer commands requiring these file settings should be run from this work directory, as should the **import** wrapper script itself.

Once configured, update the actions-importer to the latest version with: "$ gh actions-importer update"

At this point you are ready to run the full suite of gh actions-import workflow commands: audit/forecast/dry-run/migrate and the **import** wrapper script.

Note that the migrate function needs a non-empty repo on the Github (target) side - so for newly created target repos at least e.g. a README or similar is required.

## Runtime and example output

Run **import** with: "$ import"

The **ComputeAorta** directory in the **import** repo (this repo) - and all its contents - represent output from an example **import** run using the following settings:

GITLAB (SOURCE) NAMESPACE / GROUP: **ComputeAorta**

GITLAB (SOURCE) REPO: **ca-llvm**

GITHUB (TARGET) REPO: **alan-forbes-cp/import_target**

These can be tailored in the **import** script as required for individual runs. Note that the script contains a "TO DO:" list of future improvements - including the addition of command-line options for per-run Gitlab/Github settings. 

The **import** script uses the **gh** (Github CLI) command and its **actions-importer** extension. Example output of the following 4 actions-importer functions used is shown in sub-directories under the **ComputeAorta** directory:
1. audit (aka plan)
2. forecast
3. dry-run
4. migrate

These sub-directories are created by a single **import** run. Taken in the above order, they represent a typical action **import** workflow.

**audit** and **forecast** operate at **ComputeAorta** (source group) level. **dry-run** operates at **ca-llvm** (source repo) level. **migrate** operates at **ca-llvm**/**import_target** (source repo/target repo) level.

The **_command.out** files in the **ComputeAorta** directory contain the actual console output for each actions-importer operation and are included for completeness. You may need to "cat" these files at a console to get readable output.

Browsing each of the sub-directories under **ComputeAorta** should provide a flavour of the typical output for each of the actions-importer functions. In particular, note the following files from the audit (or plan), forecast and dry-run phases:

[ComputeAorta audit summary](https://github.com/alan-forbes-cp/import/blob/master/ComputeAorta/audit/audit_summary.md)

[ComputeAorta forecast report](https://github.com/alan-forbes-cp/import/blob/master/ComputeAorta/forecast/forecast_report.md)

[Dry-run generated ca-llvm Github action workflow .yml file](https://github.com/alan-forbes-cp/import/blob/master/ComputeAorta/dry-run/ComputeAorta/ca-llvm/.github/workflows/ca-llvm.yml)

The final migrate phase results in a PR being created in the target Github repo. For the **import** run used to populate the **ComputeAorta** sub-directories, the corresponding [PR can be found here](https://github.com/alan-forbes-cp/import_target/pull/1). Note that the file proposed for merging is the same .yml file as in the above-mentioned dry-run phase.

There is a useful workflow overview here: https://www.youtube.com/watch?v=3t5ywu0_qk4

## FYI: actions-importer gotchas and known import limitations @ version: 1.3.22081

In no particular order:
- actions-importer can get confused by very complex Gitlab CI pipeline definitions - particularly those using multiple levels of nested included files. Check that **all** pipeline jobs have been imported successfully with no omissions - do not assume that a default import run "pass" implies a complete import of all jobs. Note: worst case you may have to refactor/simplify your source pipeline and re-import.
- initial action runs of imported pipelines may reveal 'invalid workflow' errors which are not otherwise documented during import. For example, actions-importer may not handle Gitlab's i. **!reference** tags or ii. pipeline parameter definition syntax. Your workflow may fail out-the-box as a result. Note: current thinking is that Github's 'customs tranformations' function may be useful to automatically convert the offending syntax in these situations. Alternatively, a local post-import processing tool could be used as an additional pass to tidy them up. That's all TBD. There is also some speculation that these issues may in part be due to the actions-importer tool taking an old version of Gitlab pipelines as its reference version - however that's not confirmed.
- check that your generated workflow action .yml file doesn't include any "not transformed" warnings as these will need manual intervention despite not being lised in your PRs "manual steps"  e.g.:

    `'artifacts.junit' was not transformed because there is no suitable equivalent in GitHub Actions`

- as should be clear from the above, the official actions-importer "manual steps" may be only a starting point towards creating a functional Github workflow. Check the generated .yml carefully for further warnings, errors and omissions.
