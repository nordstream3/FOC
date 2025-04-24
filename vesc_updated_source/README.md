Apply the Patch

On the target system, ensure you have a copy of dir_original (e.g vesc v. 6.05) and apply the patch using patch:

patch -p1 -d dir_original < updates.patch

example:
patch -p2 -d ./bldc-release_6_05 < vesc_foc_king20_bmi270.patch

Explanation:
-p1: Strips the first level of directory from the paths in the patch.
-d dir_original: Changes to the directory where the patch should be applied.
