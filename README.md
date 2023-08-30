# DPDK_SVE_PATCH

Track Link on DPDK Mailing List - http://patches.dpdk.org/project/dpdk/patch/20230817212417.3637080-2-Harjot.Singh@arm.com/

- Implemented Vector Length Agnostic SVE code for comparing signatures
in bulk lookup.
- Added Defines in code for SVE code support.
processor.

Performance Numbers from hash_perf_autotest :

Elements in Primary or Secondary Location

Results (in CPU cycles/operation)
-----------------------------------
 Operations without data

Without pre-computed hash values

Keysize     Add/Lookup/Lookup_bulk
            Neon         SVE
4           93/71/26     93/71/27
8           93/70/26     93/70/27
9           94/74/27     94/74/28
13          100/80/31    100/79/32
16          100/78/30    100/78/31
32          109/110/38   108/110/39

With pre-computed hash values

Keysize     Add/Lookup/Lookup_bulk
            Neon         SVE
4           83/58/27     83/58/29
8           83/57/27     83/57/28
9           83/60/28     83/60/29
13          84/60/28     83/60/29
16          83/58/27     83/58/29
32          84/68/31     84/68/32
