FakeDreamer Kernel Builder using github action

Currently support alioth, apollo and munch.

Notes:
1. Tester workflow build from branch from workflow input
2. Release workflow builds from next-main, next-susfs and no-ksu branches respectively,
   if you want to change it to another branches please edit the workflow directly or use
   Tester workflow instead
3. Support for other Mi-Kona might be added in the future.
4. Support AOSP Clang 20 and Neutron Clang 19, more will be added in the future.

How to use:
1. For tester workflow, input:
   - Repository Link
   - Branch
   - Compiler
   - LTO (Default FullLTO)
2. Run with nextpatch.sh (required to fetch latest KSUNext)
   If you want to skip it, please modify your Repo according to your needs
3. Default is using undervolted GPU Freq and using a patch to add make it Stock GPU Freq
   (This might be changed in the future)
4. Run the workflow, output will be a single .zip file with:
   - Alioth = (4 dtbo, 4 dtb and 1 Image.gz)
   - The rest = (2 dtbo, 4 dtb and 1 Image.gz)

Additional features:
1. OPLUS features for some oplus ports to work properly (this needs changes in the kernel repo)
2. Skip nextpatch.sh if you don't need it

If you found any issue, contact me on Telegram (@KaminariKo).
