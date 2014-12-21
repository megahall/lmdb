# liblmdb - Symas Lightning Memory-Mapped Database (LMDB) #

This is an unofficial fork by Matthew Hall.

## Changes in fork ##

1. Compiled with clang.
2. Compiled to special prefix for use with:
   [SDN Sensor](https://github.com/megahall/sdn_sensor).
3. Uses the explicit jemalloc memory allocator.
   `malloc`, `calloc`, `realloc`, `free`, `strdup` and `strndup`
   are replaced with the `je_*` equivalents.
   A `je_utils.c` file is present for `je_strdup` and `je_strndup`.
4. The `testdb` used in the unit tests is moved to `/tmp`.
   Vagrant and other VM shared filesystems cannot `mmap`.
