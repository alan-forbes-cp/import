# Audit summary

Summary for [GitLab instance](https://10.54.10.74/ComputeAorta)

- GitHub Actions Importer version: **1.3.22081 (ff41350a9d6afd71f38535f23e39fff593ed049c)**
- Performed at: **7/30/24 at 12:20**

## Pipelines

Total: **14**

- Successful: **8 (57%)**
- Partially successful: **0 (0%)**
- Unsupported: **1 (7%)**
- Failed: **5 (35%)**

### Job types

Supported: **13 (92%)**

- YAML: **13**

Unsupported: **1 (7%)**

- None: **1**

### Build steps

Total: **1080**

Known: **1057 (97%)**

- script: **484**
- before_script: **412**
- checkout: **119**
- dependencies: **25**
- artifacts: **8**
- after_script: **6**
- trigger: **2**
- pages: **1**

Unsupported: **23 (2%)**

- artifacts.junit: **22**
- artifacts.dotenv: **1**

Actions: **1058**

- run: **904**
- actions/checkout@v4.1.0: **119**
- actions/download-artifact@v4.1.0: **25**
- actions/upload-artifact@v4.1.0: **8**
- JamesIves/github-pages-deploy-action@v4.5.0: **1**
- ./.github/workflows/.gitlab-ci-nightly_pipeline.yml: **1**

### Triggers

Total: **34**

Known: **34 (100%)**

- schedule: **10**
- manual: **8**
- merge_request: **8**
- push: **8**

Actions: **27**

- schedule: **9**
- workflow_dispatch: **8**
- push: **8**
- pull_request: **2**

### Environment

Total: **0**

Actions: **105**

- LLVM_GIT_WRITE_TOKEN: **8**
- CA_GITLAB_API_TOKEN: **8**
- CA_GIT_WRITE_TOKEN: **8**
- GTEST_COLOR: **8**
- CLICOLOR_FORCE: **8**
- OLD_CA_GIT_WRITE_TOKEN: **8**
- OLD_CA_GITLAB_API_TOKEN: **8**
- SCCACHE_REDIS: **8**
- ComputeAortaCLVK_TOKEN: **8**
- ComputeAortaCL_TOKEN: **8**
- ZULIP_TOKEN: **8**
- STORAGE_PASS: **8**
- STORAGE_USER: **8**
- COMPUTECPP_DISTRIBUTION: **1**

### Other

Total: **8**

Known: **8 (100%)**

- auto_cancel_pending_pipelines: **8**

Actions: **2577**

- image: **113**
- GITHUB_USER: **76**
- GIT_STRATEGY: **70**
- LLVM_VERSION: **44**
- CA_CTS_TYPE_RISCV: **40**
- RUN_DOC: **40**
- RUN_BUILD_TEST: **40**
- BUILD_LLVM_BRANCHNAME: **40**
- BUILD_LLVM_CALLVM_BRANCH: **40**
- SEND_ZULIP: **40**
- BUILD_DPCPP_BRANCH: **40**
- RUN_NATIVE_CPU_SYCL_CTS: **40**
- RUN_REMOTE_HAL: **40**
- RUN_WEIRD_PIPELINE: **40**
- RUN_LINUX_RISCV: **40**
- RUN_LINUX_HOST: **40**
- RUN_RISCV_CROSS_HOST: **40**
- RUN_ARM_CROSS_HOST: **40**
- RUN_WINDOWS_HOST: **40**
- RUN_SYCL_CTS: **40**
- RUN_SYCL_LLVM: **40**
- MR_TARGET_BRANCH: **40**
- CA_CTS_TYPE_ARM: **40**
- CA_CTS_TYPE_X86: **40**
- RUN_BUILD_LLVM: **40**
- CA_LLVM_BRANCH: **40**
- CA_PIPELINE_TYPE: **40**
- MERGE_TO_STABLE: **40**
- LLVM_PREVIOUS: **40**
- LLVM_LATEST: **40**
- RUN_SANITIZERS: **40**
- RUN_TIDY: **40**
- OCK_BRANCH: **40**
- MUX_TARGET: **36**
- COMPUTECPP_CUSTOM_RELEASE: **36**
- COMPUTECPP_VERSION: **36**
- BUILD_CA_ARTEFACT: **36**
- CA_BRANCH: **36**
- CONFIG: **36**
- PROJECT: **36**
- GIT_DEPTH: **30**
- NIGHTLY_CA_CTS_TYPE_X86: **22**
- NIGHTLY_CA_CTS_TYPE_ARM: **22**
- NIGHTLY_CA_CTS_TYPE_RISCV: **22**
- NIGHTLY_OCK_BRANCH: **22**
- NIGHTLY_SEND_ZULIP: **22**
- NIGHTLY_RUN_TIDY: **22**
- NIGHTLY_BUILD_LLVM_BRANCHNAME: **22**
- NIGHTLY_BUILD_LLVM_CALLVM_BRANCH: **22**
- NIGHTLY_RUN_BUILD_LLVM: **22**
- NIGHTLY_RUN_SANITIZERS: **22**
- NIGHTLY_RUN_LINUX_RISCV: **22**
- NIGHTLY_RUN_LINUX_HOST: **22**
- NIGHTLY_RUN_ARM_CROSS_HOST: **22**
- NIGHTLY_RUN_WINDOWS_HOST: **22**
- NIGHTLY_RUN_WEIRD_PIPELINE: **22**
- NIGHTLY_CA_HAVE_NATIVE_AARCH64: **22**
- NIGHTLY_MERGE_TO_STABLE: **22**
- NIGHTLY_GITHUB_USER: **22**
- NIGHTLY_LLVM_PREVIOUS: **22**
- NIGHTLY_LLVM_LATEST: **22**
- PLATFORM: **21**
- BuildType: **18**
- Arch: **18**
- LLVMBranch: **18**
- Target: **18**
- Images: **18**
- CommandBuffer: **18**
- USM: **18**
- FP16: **18**
- Compiler: **18**
- LLVM_BRANCH: **11**
- BUILD_ID: **10**
- TARGET: **9**
- SHAREDSTORAGE_NAME: **9**
- DRY_RUN: **9**
- PUSH_TAG: **9**
- ZULIP_PIPELINE_NAME: **9**
- cancel_in_progress: **8**
- group: **8**
- BUILD_WINDOWS_X86: **8**
- MUX_COMPILERS_TO_ENABLE: **8**
- BUILD_LINUX_X86: **8**
- BUILD_LINUX_ARM: **8**
- BUILD_LINUX_RISCV: **8**
- LLVM_REPO: **8**
- ZULIP_TOPIC: **7**
- ZULIP_STREAM: **7**
- EXTERNAL_MUX_COMPILER_DIRS: **7**
- HAL_REFSI_SOC: **7**
- HAL_REFSI_THREAD_MODE: **7**
- HAL_DESCRIPTION: **6**
- ZULIP_STATUS_BADGE: **6**
- ARTEFACT_CHECKOUT_PATH: **5**
- DISABLE_VECZ_CHECKS: **5**
- CLC_BUILD_ID: **4**
- ZULIP_STATUS: **3**
- ONEAPI_CON_KIT_DIR: **3**
- HOST_TARGET_CPU: **2**
- CA_INSTALL_DIR: **2**
- BUILD_TYPE: **2**
- ARCH: **2**
- RUN_PREFIX: **2**
- DISTRIB_ID: **1**
- INTEGRATION_PROJECT_ID: **1**

### Manual tasks

Total: **73**

Secrets: **72**

- `${{ secrets.STORAGE_USER }}`: **8**
- `${{ secrets.STORAGE_PASS }}`: **8**
- `${{ secrets.ZULIP_TOKEN }}`: **8**
- `${{ secrets.ComputeAortaCL_TOKEN }}`: **8**
- `${{ secrets.ComputeAortaCLVK_TOKEN }}`: **8**
- `${{ secrets.OLD_CA_GITLAB_API_TOKEN }}`: **8**
- `${{ secrets.OLD_CA_GIT_WRITE_TOKEN }}`: **8**
- `${{ secrets.CA_GIT_WRITE_TOKEN }}`: **8**
- `${{ secrets.CA_GITLAB_API_TOKEN }}`: **8**

Self hosted runners: **1**

- `linux-docker-images`: **1**

### Successful

#### ComputeAorta/ci-github

- [ComputeAorta/ci-github/.github/workflows/ci-github.yml](ComputeAorta/ci-github/.github/workflows/ci-github.yml)
- [ComputeAorta/ci-github/.github/workflows/.gitlab-ci-nightly_pipeline.yml](ComputeAorta/ci-github/.github/workflows/.gitlab-ci-nightly_pipeline.yml)
- [ComputeAorta/ci-github/config.json](ComputeAorta/ci-github/config.json)
- [ComputeAorta/ci-github/source.yml](ComputeAorta/ci-github/source.yml)

#### ComputeAorta/ecosystem-test-scripts

- [ComputeAorta/ecosystem-test-scripts/.github/workflows/ecosystem-test-scripts.yml](ComputeAorta/ecosystem-test-scripts/.github/workflows/ecosystem-test-scripts.yml)
- [ComputeAorta/ecosystem-test-scripts/config.json](ComputeAorta/ecosystem-test-scripts/config.json)
- [ComputeAorta/ecosystem-test-scripts/source.yml](ComputeAorta/ecosystem-test-scripts/source.yml)

#### ComputeAorta/CI

- [ComputeAorta/CI/.github/workflows/ci.yml](ComputeAorta/CI/.github/workflows/ci.yml)
- [ComputeAorta/CI/config.json](ComputeAorta/CI/config.json)
- [ComputeAorta/CI/source.yml](ComputeAorta/CI/source.yml)

#### ComputeAorta/CA-OpenCL-CTS

- [ComputeAorta/CA-OpenCL-CTS/.github/workflows/ca-opencl-cts.yml](ComputeAorta/CA-OpenCL-CTS/.github/workflows/ca-opencl-cts.yml)
- [ComputeAorta/CA-OpenCL-CTS/config.json](ComputeAorta/CA-OpenCL-CTS/config.json)
- [ComputeAorta/CA-OpenCL-CTS/source.yml](ComputeAorta/CA-OpenCL-CTS/source.yml)

#### ComputeAorta/Handbook

- [ComputeAorta/Handbook/.github/workflows/handbook.yml](ComputeAorta/Handbook/.github/workflows/handbook.yml)
- [ComputeAorta/Handbook/config.json](ComputeAorta/Handbook/config.json)
- [ComputeAorta/Handbook/source.yml](ComputeAorta/Handbook/source.yml)

#### ComputeAorta/ca-llvm

- [ComputeAorta/ca-llvm/.github/workflows/ca-llvm.yml](ComputeAorta/ca-llvm/.github/workflows/ca-llvm.yml)
- [ComputeAorta/ca-llvm/config.json](ComputeAorta/ca-llvm/config.json)
- [ComputeAorta/ca-llvm/source.yml](ComputeAorta/ca-llvm/source.yml)

#### ComputeAorta/build_tools

- [ComputeAorta/build_tools/.github/workflows/build_tools.yml](ComputeAorta/build_tools/.github/workflows/build_tools.yml)
- [ComputeAorta/build_tools/config.json](ComputeAorta/build_tools/config.json)
- [ComputeAorta/build_tools/source.yml](ComputeAorta/build_tools/source.yml)

#### ComputeAorta/PerfCL

- [ComputeAorta/PerfCL/.github/workflows/perfcl.yml](ComputeAorta/PerfCL/.github/workflows/perfcl.yml)
- [ComputeAorta/PerfCL/config.json](ComputeAorta/PerfCL/config.json)
- [ComputeAorta/PerfCL/source.yml](ComputeAorta/PerfCL/source.yml)

### Unsupported

#### ComputeAorta/oneapi-construction-kit

- [ComputeAorta/oneapi-construction-kit/error.txt](ComputeAorta/oneapi-construction-kit/error.txt)
- [ComputeAorta/oneapi-construction-kit/config.json](ComputeAorta/oneapi-construction-kit/config.json)

### Failed

#### ComputeAorta/oneapi-construction-kit

- [ComputeAorta/oneapi-construction-kit/error.txt](ComputeAorta/oneapi-construction-kit/error.txt)
- [ComputeAorta/oneapi-construction-kit/config.json](ComputeAorta/oneapi-construction-kit/config.json)

#### webservices/acoran-for-risc-v-documentation

- [webservices/acoran-for-risc-v-documentation/error.txt](webservices/acoran-for-risc-v-documentation/error.txt)

#### ComputeAorta/ci-experiments

- [ComputeAorta/ci-experiments/error.txt](ComputeAorta/ci-experiments/error.txt)

#### ComputeAorta/HAL

- [ComputeAorta/HAL/error.txt](ComputeAorta/HAL/error.txt)

#### ComputeAorta/VK

- [ComputeAorta/VK/error.txt](ComputeAorta/VK/error.txt)

#### ComputeAorta/ComputeAorta

- [ComputeAorta/ComputeAorta/error.txt](ComputeAorta/ComputeAorta/error.txt)
