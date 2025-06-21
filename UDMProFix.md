# Can the UDMPro be fixed from "Really bricked"?

Short answer, not yet...

We need your help.

At the core of the issue is corrupt boot_straps. Perhaps, during an upgrade the AL324 SOC flash memory layout from v1 or v2 to v3, it corruppted the i2c_pld. The sourcecode memtions three versions of reg_print_offsets_i2c_pld.

Can anyone provide feedback on any method to update the flash memory on the AL324 ? Please post a comment.