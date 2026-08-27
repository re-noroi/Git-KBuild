# FakeDreamer Kernel Builder

An automated kernel builder using GitHub Actions. 

## 📱 Supported Devices
*   **alioth**
*   **apollo**
*   **munch**
*(Note: Support for other Mi-Kona devices may be added in the future.)*

## 🛠️ Features & Specifications
*   **Supported Compilers:** Clang (`r547379`, `r574158`, `r614150`) and Neutron-Clang `24.0.0`.
*   **GPU Frequencies:** Defaults to an undervolted GPU frequency, utilizing a patch to revert to stock GPU frequency (subject to change).
*   **OPLUS Features:** Optional support for OPLUS ports to function properly. This can be easily toggled during the workflow setup (requires specific changes in the target kernel repository).

## 🚀 How to Use
1.  Navigate to the **Actions** tab in this repository.
2.  Select either the **Tester** or **Release** workflow.
3.  Click **Run workflow** and configure the following parameters:
    *   **AnyKernel Repo:** Link to your preferred AnyKernel3 repository (e.g., `https://github.com/re-noroi/anykernel3-test`).
    *   **Custom Kernel Version:** Suffix for your kernel build (e.g., `-FakeDreamer`).
    *   **Choose compiler:** Select your preferred compiler (e.g., `neutron`).
    *   **LTO_CHOICE:** Choose your Link-Time Optimization level (defaults to `full_lto`).
    *   **OPLUS features toggle:** Select `yes` or `no` depending on if you need OPLUS specific features enabled.
4.  Run the workflow. 

## 📦 Outputs
The workflow will generate a single `.zip` archive containing the following:
*   **Alioth:** 4 `dtbo`, 4 `dtb`, and 1 `Image.gz`
*   **Apollo / Munch:** 2 `dtbo`, 4 `dtb`, and 1 `Image.gz`

**Workflow Differences:**
*   **Tester Workflows:** Outputs a `TEST` version archive.
*   **Release Workflows:** Outputs both `ksu` and `noksu` archives.

## ⚠️ Notes & Deprecations
*   Workflows now build directly from the main branch inputs (unified workflow).
*   The `SUSFS` branch is officially deprecated.
*   Execution with `nextpatch.sh` has been removed (as of 27/08/2026).

## 📞 Contact
If you find any issues, contact me on Telegram: [@KaminariKo](https://t.me/KaminariKo).

---
*Last Updated: 27/08/2026*