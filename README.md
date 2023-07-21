|        KERNEL        | CMAKE-BUILD-DIRECTORY |            BUILD-KERNEL-MODULE            |            SCAP-OPEN-AND-KERNEL-MODULE            |            BUILD-BPF-PROBE            |            SCAP-OPEN-AND-BPF-PROBE            |            SCAP-OPEN-AND-MODERN-PROBE             |
|----------------------|-----------------------|-------------------------------------------|---------------------------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------------|
| amazonlinux2-4.19    | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| amazonlinux2-5.10    | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| amazonlinux2-5.15    | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| amazonlinux2-5.4     | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| amazonlinux2022-5.15 | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| amazonlinux2023-6.1  | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| archlinux-5.18       | 🟢                    | [❌](#archlinux-5.18-build-kernel-module) | [❌](#archlinux-5.18-scap-open-and-kernel-module) | 🟢                                    | 🟢                                            | 🟢                                                |
| archlinux-6.0        | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| centos-3.10          | 🟢                    | 🟢                                        |                                                   | 🟢                                    | 🟢                                            | 🟢                                                |
| centos-4.18          | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| centos-5.14          | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| centos-builder       | 🟢                    | [🟡](#centos-builder-build-kernel-module) | [🟡](#centos-builder-scap-open-and-kernel-module) | [🟡](#centos-builder-build-bpf-probe) | [🟡](#centos-builder-scap-open-and-bpf-probe) | 🟢                                                |
| fedora-5.17          | 🟢                    | [🟡](#fedora-5.17-build-kernel-module)    | [❌](#fedora-5.17-scap-open-and-kernel-module)    | 🟢                                    | 🟢                                            | 🟢                                                |
| fedora-5.8           | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | [❌](#fedora-5.8-scap-open-and-bpf-probe)     | 🟢                                                |
| fedora-6.2           | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| fedora-builder       | 🟢                    | [🟡](#fedora-builder-build-kernel-module) | [🟡](#fedora-builder-scap-open-and-kernel-module) | [🟡](#fedora-builder-build-bpf-probe) | [🟡](#fedora-builder-scap-open-and-bpf-probe) | 🟢                                                |
| oraclelinux-3.10     | 🟢                    | 🟢                                        |                                                   | 🟢                                    | 🟢                                            | 🟢                                                |
| oraclelinux-4.14     | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| oraclelinux-5.15     | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| oraclelinux-5.4      | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | [❌](#oraclelinux-5.4-scap-open-and-modern-probe) |
| ubuntu-4.15          | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |
| ubuntu-6.3           | 🟢                    | 🟢                                        | 🟢                                                | 🟢                                    | 🟢                                            | 🟢                                                |


# archlinux-5.18 build-kernel-module

Msg:
```
non-zero return code
```
Err:
```
insmod: ERROR: could not insert module driver/scap.ko: Invalid parameters
```

# archlinux-5.18 scap-open-and-kernel-module

Msg:
```
non-zero return code
```
Err:
```
error opening device /dev/scap0. Make sure you have root credentials and that the scap module is loaded: No such file or directory (1)
```

# centos-builder build-kernel-module

Msg:
```
non-zero return code
```
Err:
```
make: *** /lib/modules/5.14.0-325.el9.x86_64/build: No such file or directory.  Stop.
make[4]: *** [all] Error 2
make[3]: *** [driver/CMakeFiles/driver] Error 2
make[2]: *** [driver/CMakeFiles/driver.dir/all] Error 2
make[1]: *** [driver/CMakeFiles/driver.dir/rule] Error 2
make: *** [driver] Error 2
```

# centos-builder scap-open-and-kernel-module

Msg:
```
[Errno 2] No such file or directory
```
Err:
```

```

# centos-builder build-bpf-probe

Msg:
```
non-zero return code
```
Err:
```
expr: syntax error
/bin/sh: clang: command not found
expr: syntax error
make[4]: warning: jobserver unavailable: using -j1.  Add `+' to parent make rule.
make: *** /lib/modules/5.14.0-325.el9.x86_64/build: No such file or directory.  Stop.
make[4]: *** [all] Error 2
make[3]: *** [driver/bpf/CMakeFiles/bpf] Error 2
make[2]: *** [driver/bpf/CMakeFiles/bpf.dir/all] Error 2
make[1]: *** [driver/bpf/CMakeFiles/bpf.dir/rule] Error 2
make: *** [bpf] Error 2
```

# centos-builder scap-open-and-bpf-probe

Msg:
```
[Errno 2] No such file or directory
```
Err:
```

```

# fedora-5.17 build-kernel-module

Msg:
```
non-zero return code
```
Err:
```
warning: the compiler differs from the one used to build the kernel
  The kernel was built by: gcc (GCC) 12.0.1 20220413 (Red Hat 12.0.1-0)
  You are using:           gcc (GCC) 12.2.1 20221121 (Red Hat 12.2.1-4)
/root/repos/falcosecurity-libs/build/driver/src/main.c: In function ‘scap_init’:
/root/repos/falcosecurity-libs/build/driver/src/main.c:2893:30: error: assignment to ‘char * (*)(struct device *, umode_t *)’ {aka ‘char * (*)(struct device *, short unsigned int *)’} from incompatible pointer type ‘char * (*)(const struct device *, umode_t *)’ {aka ‘char * (*)(const struct device *, short unsigned int *)’} [-Werror=incompatible-pointer-types]
 2893 |         g_ppm_class->devnode = ppm_devnode;
      |                              ^
cc1: some warnings being treated as errors
make[6]: *** [scripts/Makefile.build:288: /root/repos/falcosecurity-libs/build/driver/src/main.o] Error 1
make[6]: *** Waiting for unfinished jobs....
make[5]: *** [Makefile:1841: /root/repos/falcosecurity-libs/build/driver/src] Error 2
make[4]: *** [Makefile:16: all] Error 2
make[3]: *** [driver/CMakeFiles/driver.dir/build.make:70: driver/CMakeFiles/driver] Error 2
make[2]: *** [CMakeFiles/Makefile2:595: driver/CMakeFiles/driver.dir/all] Error 2
make[1]: *** [CMakeFiles/Makefile2:602: driver/CMakeFiles/driver.dir/rule] Error 2
make: *** [Makefile:273: driver] Error 2
```

# fedora-5.17 scap-open-and-kernel-module

Msg:
```
non-zero return code
```
Err:
```
error opening device /dev/scap0. Make sure you have root credentials and that the scap module is loaded: No such file or directory (1)
```

# fedora-5.8 scap-open-and-bpf-probe

Msg:
```
non-zero return code
```
Err:
```
-- BEGIN PROG LOAD LOG --
0: (bf) r6 = r1
1: (b7) r1 = 0
2: (63) *(u32 *)(r10 -8) = r1
last_idx 2 first_idx 0
regs=2 stack=0 before 1: (b7) r1 = 0
3: (bf) r2 = r10
4: (07) r2 += -8
5: (18) r1 = 0xffff88807320ee00
7: (85) call bpf_map_lookup_elem#1
8: (15) if r0 == 0x0 goto pc+2774
 R0_w=map_value(id=0,off=0,ks=4,vs=35,imm=0) R6_w=ctx(id=0,off=0,imm=0) R10=fp0 fp-8=????mmmm
9: (85) call bpf_get_smp_processor_id#8
10: (bf) r9 = r0
11: (63) *(u32 *)(r10 -8) = r9
12: (bf) r2 = r10
13: (07) r2 += -8
14: (18) r1 = 0xffffc90000708000
16: (85) call bpf_map_lookup_elem#1
17: (bf) r8 = r0
18: (15) if r8 == 0x0 goto pc+2764
 R0_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R6=ctx(id=0,off=0,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv(id=0) R10=fp0 fp-8=????mmmm
19: (63) *(u32 *)(r10 -8) = r9
20: (bf) r2 = r10
21: (07) r2 += -8
22: (18) r1 = 0xffff888073259c00
24: (85) call bpf_map_lookup_elem#1
25: (bf) r7 = r0
26: (15) if r7 == 0x0 goto pc+2756
 R0=map_value(id=0,off=0,ks=4,vs=181,imm=0) R6=ctx(id=0,off=0,imm=0) R7_w=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=inv(id=0) R10=fp0 fp-8=????mmmm
27: (7b) *(u64 *)(r10 -16) = r8
28: (63) *(u32 *)(r10 -8) = r9
29: (bf) r2 = r10
30: (07) r2 += -8
31: (18) r1 = 0xffffc9000078a000
33: (85) call bpf_map_lookup_elem#1
34: (18) r3 = 0xfffffffd
36: (15) if r0 == 0x0 goto pc+2737
 R0=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=inv(id=0) R10=fp0 fp-8=????mmmm fp-16=map_value
37: (71) r1 = *(u8 *)(r7 +1)
 R0=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=inv(id=0) R10=fp0 fp-8=????mmmm fp-16=map_value
38: (67) r1 <<= 8
39: (71) r2 = *(u8 *)(r7 +0)
 R0=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R1_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=inv(id=0) R10=fp0 fp-8=????mmmm fp-16=map_value
40: (4f) r1 |= r2
41: (71) r2 = *(u8 *)(r7 +2)
 R0=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R1_w=inv(id=0) R2_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=inv(id=0) R10=fp0 fp-8=????mmmm fp-16=map_value
42: (71) r3 = *(u8 *)(r7 +3)
 R0=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R1_w=inv(id=0) R2_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=inv(id=0) R10=fp0 fp-8=????mmmm fp-16=map_value
43: (67) r3 <<= 8
44: (4f) r3 |= r2
45: (67) r3 <<= 16
46: (4f) r3 |= r1
47: (63) *(u32 *)(r10 -8) = r3
48: (bf) r2 = r10
49: (07) r2 += -8
50: (18) r1 = 0xffffc90000549000
52: (85) call bpf_map_lookup_elem#1
53: (bf) r9 = r0
54: (18) r3 = 0xfffffffd
56: (15) if r9 == 0x0 goto pc+2717
 R0=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
57: (71) r1 = *(u8 *)(r7 +1)
 R0=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
58: (67) r1 <<= 8
59: (71) r2 = *(u8 *)(r7 +0)
 R0=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R1_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
60: (4f) r1 |= r2
61: (71) r2 = *(u8 *)(r7 +2)
 R0=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R1_w=inv(id=0) R2_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
62: (71) r3 = *(u8 *)(r7 +3)
 R0=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R1_w=inv(id=0) R2_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
63: (67) r3 <<= 8
64: (4f) r3 |= r2
65: (67) r3 <<= 16
66: (4f) r3 |= r1
67: (63) *(u32 *)(r10 -8) = r3
68: (bf) r2 = r10
69: (07) r2 += -8
70: (18) r1 = 0xffff88805ada8000
72: (85) call bpf_map_lookup_elem#1
73: (18) r3 = 0xfffffffd
75: (15) if r0 == 0x0 goto pc+2698
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
76: (71) r1 = *(u8 *)(r7 +29)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
77: (67) r1 <<= 8
78: (71) r2 = *(u8 *)(r7 +28)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
79: (4f) r1 |= r2
80: (71) r2 = *(u8 *)(r7 +31)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
81: (67) r2 <<= 8
82: (71) r3 = *(u8 *)(r7 +30)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
83: (4f) r2 |= r3
84: (67) r2 <<= 16
85: (4f) r2 |= r1
86: (71) r3 = *(u8 *)(r7 +33)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0) R3_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
87: (67) r3 <<= 8
88: (71) r1 = *(u8 *)(r7 +32)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0) R3_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
89: (4f) r3 |= r1
90: (71) r4 = *(u8 *)(r7 +34)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R2_w=inv(id=0) R3_w=inv(id=0) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
91: (71) r1 = *(u8 *)(r7 +35)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R2_w=inv(id=0) R3_w=inv(id=0) R4_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
92: (67) r1 <<= 8
93: (4f) r1 |= r4
94: (67) r1 <<= 16
95: (4f) r1 |= r3
96: (67) r1 <<= 32
97: (4f) r1 |= r2
98: (15) if r1 == 0x0 goto pc+26
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0) R3_w=inv(id=0) R4_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
99: (71) r2 = *(u8 *)(r7 +21)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0) R3_w=inv(id=0) R4_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
100: (67) r2 <<= 8
101: (71) r3 = *(u8 *)(r7 +20)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R3_w=inv(id=0) R4_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
102: (4f) r2 |= r3
103: (71) r3 = *(u8 *)(r7 +23)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0) R3_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R4_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
104: (67) r3 <<= 8
105: (71) r4 = *(u8 *)(r7 +22)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0) R3_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R4_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
106: (4f) r3 |= r4
107: (67) r3 <<= 16
108: (4f) r3 |= r2
109: (71) r4 = *(u8 *)(r7 +25)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0) R3_w=inv(id=0) R4_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
110: (67) r4 <<= 8
111: (71) r2 = *(u8 *)(r7 +24)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0) R3_w=inv(id=0) R4_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
112: (4f) r4 |= r2
113: (71) r2 = *(u8 *)(r7 +27)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R3_w=inv(id=0) R4_w=inv(id=0) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
114: (67) r2 <<= 8
115: (71) r5 = *(u8 *)(r7 +26)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R3_w=inv(id=0) R4_w=inv(id=0) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value
116: (4f) r2 |= r5
117: (67) r2 <<= 16
118: (4f) r2 |= r4
119: (67) r2 <<= 32
120: (4f) r2 |= r3
121: (bf) r3 = r7
122: (07) r3 += 20
123: (7b) *(u64 *)(r10 -32) = r3
124: (05) goto pc+85
210: (18) r3 = 0xfffffffb
212: (25) if r2 > 0x1ffff goto pc+2561
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1=inv(id=0) R2=inv(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=inv4294967291 R4=inv(id=0) R5=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value
213: (79) r4 = *(u64 *)(r6 +8)
214: (79) r8 = *(u64 *)(r10 -16)
215: (bf) r3 = r8
216: (0f) r3 += r2
last_idx 216 first_idx 210
regs=4 stack=0 before 215: (bf) r3 = r8
regs=4 stack=0 before 214: (79) r8 = *(u64 *)(r10 -16)
regs=4 stack=0 before 213: (79) r4 = *(u64 *)(r6 +8)
regs=4 stack=0 before 212: (25) if r2 > 0x1ffff goto pc+2561
regs=4 stack=0 before 210: (18) r3 = 0xfffffffb
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1_w=inv(id=0) R2_rw=invP(id=0) R3_w=map_value(id=0,off=20,ks=4,vs=181,imm=0) R4_w=inv(id=0) R5_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6_r=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16_r=map_value fp-32_w=map_value
parent didn't have regs=4 stack=0 marks
last_idx 124 first_idx 73
regs=4 stack=0 before 124: (05) goto pc+85
regs=4 stack=0 before 123: (7b) *(u64 *)(r10 -32) = r3
regs=4 stack=0 before 122: (07) r3 += 20
regs=4 stack=0 before 121: (bf) r3 = r7
regs=4 stack=0 before 120: (4f) r2 |= r3
regs=c stack=0 before 119: (67) r2 <<= 32
regs=c stack=0 before 118: (4f) r2 |= r4
regs=1c stack=0 before 117: (67) r2 <<= 16
regs=1c stack=0 before 116: (4f) r2 |= r5
regs=3c stack=0 before 115: (71) r5 = *(u8 *)(r7 +26)
regs=1c stack=0 before 114: (67) r2 <<= 8
regs=1c stack=0 before 113: (71) r2 = *(u8 *)(r7 +27)
regs=18 stack=0 before 112: (4f) r4 |= r2
regs=1c stack=0 before 111: (71) r2 = *(u8 *)(r7 +24)
regs=18 stack=0 before 110: (67) r4 <<= 8
regs=18 stack=0 before 109: (71) r4 = *(u8 *)(r7 +25)
regs=8 stack=0 before 108: (4f) r3 |= r2
regs=c stack=0 before 107: (67) r3 <<= 16
regs=c stack=0 before 106: (4f) r3 |= r4
regs=1c stack=0 before 105: (71) r4 = *(u8 *)(r7 +22)
regs=c stack=0 before 104: (67) r3 <<= 8
regs=c stack=0 before 103: (71) r3 = *(u8 *)(r7 +23)
regs=4 stack=0 before 102: (4f) r2 |= r3
regs=c stack=0 before 101: (71) r3 = *(u8 *)(r7 +20)
regs=4 stack=0 before 100: (67) r2 <<= 8
regs=4 stack=0 before 99: (71) r2 = *(u8 *)(r7 +21)
217: (7b) *(u64 *)(r10 -40) = r4
218: (7b) *(u64 *)(r3 +0) = r4
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=map_value(id=0,off=0,ks=4,vs=262144,umax_value=131071,var_off=(0x0; 0x1ffff)) R4_w=inv(id=0) R5=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
219: (71) r3 = *(u8 *)(r7 +13)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=map_value(id=0,off=0,ks=4,vs=262144,umax_value=131071,var_off=(0x0; 0x1ffff)) R4_w=inv(id=0) R5=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
220: (67) r3 <<= 8
221: (71) r4 = *(u8 *)(r7 +12)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R4_w=inv(id=0) R5=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
222: (4f) r3 |= r4
223: (71) r4 = *(u8 *)(r7 +15)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=inv(id=0) R4_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R5=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
224: (67) r4 <<= 8
225: (71) r5 = *(u8 *)(r7 +14)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=inv(id=0) R4_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R5_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
226: (4f) r4 |= r5
227: (67) r4 <<= 16
228: (4f) r4 |= r3
229: (71) r5 = *(u8 *)(r7 +17)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=inv(id=0) R4_w=inv(id=0) R5_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
230: (67) r5 <<= 8
231: (71) r3 = *(u8 *)(r7 +16)
 R0=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=inv(id=0) R4_w=inv(id=0) R5_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
232: (4f) r5 |= r3
233: (71) r0 = *(u8 *)(r7 +18)
 R0_w=map_value(id=0,off=0,ks=4,vs=58,imm=0) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R4_w=inv(id=0) R5_w=inv(id=0) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
234: (71) r3 = *(u8 *)(r7 +19)
 R0_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R4_w=inv(id=0) R5_w=inv(id=0) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
235: (67) r3 <<= 8
236: (4f) r3 |= r0
237: (67) r3 <<= 16
238: (4f) r3 |= r5
239: (67) r3 <<= 32
240: (4f) r3 |= r4
241: (bf) r4 = r3
242: (67) r4 <<= 32
243: (77) r4 >>= 32
244: (25) if r4 > 0x20 goto pc+8
 R0_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=inv(id=0) R4_w=inv(id=0,umax_value=32,var_off=(0x0; 0x3f)) R5_w=inv(id=0) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
245: (63) *(u32 *)(r10 -8) = r3
246: (61) r4 = *(u32 *)(r10 -8)
247: (57) r4 &= 31
248: (67) r4 <<= 1
249: (bf) r5 = r8
250: (0f) r5 += r4
last_idx 250 first_idx 210
regs=10 stack=0 before 249: (bf) r5 = r8
regs=10 stack=0 before 248: (67) r4 <<= 1
regs=10 stack=0 before 247: (57) r4 &= 31
regs=10 stack=0 before 246: (61) r4 = *(u32 *)(r10 -8)
251: (b7) r4 = 8
252: (6b) *(u16 *)(r5 +26) = r4
 R0_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3_w=inv(id=0) R4_w=inv8 R5_w=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9=map_value(id=0,off=0,ks=4,vs=1840,imm=0) R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40_w=mmmmmmmm
253: (b7) r9 = 0
254: (73) *(u8 *)(r7 +19) = r9
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4=inv8 R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
255: (73) *(u8 *)(r7 +18) = r9
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4=inv8 R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
256: (73) *(u8 *)(r7 +17) = r9
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4=inv8 R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
257: (73) *(u8 *)(r7 +16) = r9
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4=inv8 R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
258: (73) *(u8 *)(r7 +15) = r9
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4=inv8 R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
259: (73) *(u8 *)(r7 +14) = r9
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4=inv8 R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
260: (73) *(u8 *)(r7 +13) = r9
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4=inv8 R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
261: (07) r1 += 8
262: (bf) r4 = r1
263: (77) r4 >>= 56
264: (73) *(u8 *)(r7 +35) = r4
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
265: (bf) r4 = r1
266: (77) r4 >>= 48
267: (73) *(u8 *)(r7 +34) = r4
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=65535,var_off=(0x0; 0xffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
268: (bf) r4 = r1
269: (77) r4 >>= 40
270: (73) *(u8 *)(r7 +33) = r4
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=16777215,var_off=(0x0; 0xffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
271: (bf) r4 = r1
272: (77) r4 >>= 32
273: (73) *(u8 *)(r7 +32) = r4
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=4294967295,var_off=(0x0; 0xffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
274: (bf) r4 = r1
275: (77) r4 >>= 24
276: (73) *(u8 *)(r7 +31) = r4
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=1099511627775,var_off=(0x0; 0xffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
277: (bf) r4 = r1
278: (77) r4 >>= 16
279: (73) *(u8 *)(r7 +30) = r4
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
280: (73) *(u8 *)(r7 +28) = r1
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=inv(id=0) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
281: (77) r1 >>= 8
282: (73) *(u8 *)(r7 +29) = r1
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=inv(id=0,umax_value=72057594037927935,var_off=(0x0; 0xffffffffffffff)) R2=invP(id=0,umax_value=131071,var_off=(0x0; 0x1ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
283: (07) r2 += 8
284: (bf) r1 = r2
285: (77) r1 >>= 56
286: (73) *(u8 *)(r7 +27) = r1
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=invP0 R2_w=invP(id=0,umin_value=8,umax_value=131079,var_off=(0x0; 0x3ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
287: (bf) r1 = r2
288: (77) r1 >>= 48
289: (73) *(u8 *)(r7 +26) = r1
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=invP0 R2_w=invP(id=0,umin_value=8,umax_value=131079,var_off=(0x0; 0x3ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
290: (bf) r1 = r2
291: (77) r1 >>= 40
292: (73) *(u8 *)(r7 +25) = r1
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=invP0 R2_w=invP(id=0,umin_value=8,umax_value=131079,var_off=(0x0; 0x3ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
293: (bf) r1 = r2
294: (77) r1 >>= 32
295: (73) *(u8 *)(r7 +24) = r1
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=invP0 R2_w=invP(id=0,umin_value=8,umax_value=131079,var_off=(0x0; 0x3ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
296: (bf) r1 = r2
297: (77) r1 >>= 24
298: (73) *(u8 *)(r7 +23) = r1
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=invP0 R2_w=invP(id=0,umin_value=8,umax_value=131079,var_off=(0x0; 0x3ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
299: (bf) r1 = r2
300: (77) r1 >>= 16
301: (73) *(u8 *)(r7 +22) = r1
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=invP(id=0,umax_value=2,var_off=(0x0; 0x3),s32_max_value=3,u32_max_value=3) R2_w=invP(id=0,umin_value=8,umax_value=131079,var_off=(0x0; 0x3ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
302: (73) *(u8 *)(r7 +20) = r2
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=invP(id=0,umax_value=2,var_off=(0x0; 0x3),s32_max_value=3,u32_max_value=3) R2_w=invP(id=0,umin_value=8,umax_value=131079,var_off=(0x0; 0x3ffff)) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
303: (77) r2 >>= 8
304: (73) *(u8 *)(r7 +21) = r2
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=invP(id=0,umax_value=2,var_off=(0x0; 0x3),s32_max_value=3,u32_max_value=3) R2_w=invP(id=0,umax_value=512,var_off=(0x0; 0x3ff),s32_max_value=1023,u32_max_value=1023) R3=inv(id=0) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
305: (07) r3 += 1
306: (57) r3 &= 31
307: (73) *(u8 *)(r7 +12) = r3
 R0=inv(id=0,umax_value=255,var_off=(0x0; 0xff)) R1_w=invP(id=0,umax_value=2,var_off=(0x0; 0x3),s32_max_value=3,u32_max_value=3) R2_w=invP(id=0,umax_value=512,var_off=(0x0; 0x3ff),s32_max_value=1023,u32_max_value=1023) R3_w=inv(id=0,umax_value=31,var_off=(0x0; 0x1f)) R4_w=inv(id=0,umax_value=281474976710655,var_off=(0x0; 0xffffffffffff)) R5=map_value(id=0,off=0,ks=4,vs=262144,umax_value=62,var_off=(0x0; 0x3e)) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv0 R10=fp0 fp-8=????mmmm fp-16=map_value fp-32=map_value fp-40=mmmmmmmm
308: (85) call bpf_get_current_task#35
309: (7b) *(u64 *)(r10 -24) = r0
310: (bf) r3 = r0
311: (07) r3 += 2080
312: (bf) r1 = r10
313: (07) r1 += -8
314: (b7) r2 = 8
315: (85) call bpf_probe_read_kernel#113
last_idx 315 first_idx 253
regs=4 stack=0 before 314: (b7) r2 = 8
316: (79) r8 = *(u64 *)(r10 -8)
317: (18) r3 = 0xfffffffd
319: (15) if r8 == 0x0 goto pc+2454
 R0=inv(id=0) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=inv(id=0) R9=inv0 R10=fp0 fp-8=mmmmmmmm fp-16=map_value fp-24=mmmmmmmm fp-32=map_value fp-40=mmmmmmmm
320: (79) r1 = *(u64 *)(r10 -40)
321: (7b) *(u64 *)(r10 -48) = r8
322: (6d) if r9 s> r1 goto pc+71
 R0=inv(id=0) R1_w=inv(id=0,umax_value=9223372034707292159,var_off=(0x0; 0x7fffffff7fffffff),u32_max_value=2147483647) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=inv(id=0) R9=inv0 R10=fp0 fp-8=mmmmmmmm fp-16=map_value fp-24=mmmmmmmm fp-32=map_value fp-40=mmmmmmmm fp-48_w=mmmmmmmm
323: (bf) r3 = r8
324: (07) r3 += 320
325: (bf) r1 = r10
326: (07) r1 += -8
327: (b7) r2 = 8
328: (85) call bpf_probe_read_kernel#113
last_idx 328 first_idx 316
regs=4 stack=0 before 327: (b7) r2 = 8
329: (79) r9 = *(u64 *)(r10 -8)
330: (18) r3 = 0xfffffffd
332: (15) if r9 == 0x0 goto pc+2441
 R0=inv(id=0) R3_w=inv4294967293 R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8=inv(id=0) R9_w=inv(id=0) R10=fp0 fp-8=mmmmmmmm fp-16=map_value fp-24=mmmmmmmm fp-32=map_value fp-40=mmmmmmmm fp-48=mmmmmmmm
333: (bf) r3 = r8
334: (07) r3 += 312
335: (bf) r1 = r10
336: (07) r1 += -8
337: (b7) r2 = 8
338: (85) call bpf_probe_read_kernel#113
last_idx 338 first_idx 329
regs=4 stack=0 before 337: (b7) r2 = 8
339: (79) r3 = *(u64 *)(r10 -8)
340: (1f) r9 -= r3
341: (b7) r1 = 1
342: (79) r8 = *(u64 *)(r10 -16)
343: (bf) r4 = r9
344: (6d) if r1 s> r4 goto pc+918
 R0=inv(id=0) R1_w=inv1 R3_w=inv(id=0) R4_w=inv(id=0,umin_value=1) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv(id=0,umin_value=1) R10=fp0 fp-8=mmmmmmmm fp-16=map_value fp-24=mmmmmmmm fp-32=map_value fp-40=mmmmmmmm fp-48=mmmmmmmm
345: (79) r2 = *(u64 *)(r10 -32)
346: (71) r1 = *(u8 *)(r2 +1)
 R0=inv(id=0) R1_w=inv1 R2_w=map_value(id=0,off=20,ks=4,vs=181,imm=0) R3_w=inv(id=0) R4_w=inv(id=0,umin_value=1) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv(id=0,umin_value=1) R10=fp0 fp-8=mmmmmmmm fp-16=map_value fp-24=mmmmmmmm fp-32=map_value fp-40=mmmmmmmm fp-48=mmmmmmmm
347: (67) r1 <<= 8
348: (71) r2 = *(u8 *)(r2 +0)
 R0=inv(id=0) R1_w=inv(id=0,umax_value=65280,var_off=(0x0; 0xff00)) R2_w=map_value(id=0,off=20,ks=4,vs=181,imm=0) R3_w=inv(id=0) R4_w=inv(id=0,umin_value=1) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv(id=0,umin_value=1) R10=fp0 fp-8=mmmmmmmm fp-16=map_value fp-24=mmmmmmmm fp-32=map_value fp-40=mmmmmmmm fp-48=mmmmmmmm
349: (4f) r1 |= r2
350: (b7) r2 = 4096
351: (6d) if r2 s> r4 goto pc+1

from 351 to 353: R0=inv(id=0) R1_w=inv(id=0) R2_w=inv4096 R3_w=inv(id=0) R4_w=inv(id=0,umin_value=1) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv(id=0,umin_value=1) R10=fp0 fp-8=mmmmmmmm fp-16=map_value fp-24=mmmmmmmm fp-32=map_value fp-40=mmmmmmmm fp-48=mmmmmmmm
353: (79) r2 = *(u64 *)(r10 -32)
354: (71) r2 = *(u8 *)(r2 +2)
 R0=inv(id=0) R1_w=inv(id=0) R2_w=map_value(id=0,off=20,ks=4,vs=181,imm=0) R3_w=inv(id=0) R4_w=inv(id=0,umin_value=1) R6=ctx(id=0,off=0,imm=0) R7=map_value(id=0,off=0,ks=4,vs=181,imm=0) R8_w=map_value(id=0,off=0,ks=4,vs=262144,imm=0) R9_w=inv(id=0,umin_value=1) R10=fp0 fp-8=mmmmmmmm fp-16=map_value fp-24=mmmmmmmm fp-32=map_value fp-40=mmmmmmmm fp-48=mmmmmmmm
355: (67) r2 <<= 16
356: (4f) r2 |= r1
357: (57) r2 &= 131071
358: (bf) r1 = r8
359: (0f) r1 += r2
last_idx 359 first_idx 339
regs=4 stack=0 before 358: (bf) r1 = r8
regs=4 stack=0 before 357: (57) r2 &= 131071
regs=4 stack=0 before 356: (4f) r2 |= r1
regs=6 stack=0 before 355: (67) r2 <<= 16
regs=6 stack=0 before 354: (71) r2 = *(u8 *)(r2 +2)
regs=2 stack=0 before 353: (79) r2 = *(u64 *)(r10 -32)
regs=2 stack=0 before 351: (6d) if r2 s> r4 goto pc+1
regs=2 stack=0 before 350: (b7) r2 = 4096
regs=2 stack=0 before 349: (4f) r1 |= r2
regs=6 stack=0 before 348: (71) r2 = *(u8 *)(r2 +0)
regs=2 stack=0 before 347: (67) r1 <<= 8
regs=2 stack=0 before 346: (71) r1 = *(u8 *)(r2 +1)
360: (bf) r2 = r4
361: (bf) r9 = r4
362: (85) call bpf_probe_read_user#112
R2 unbounded memory access, use 'var &= const' or 'if (var < const)'
processed 8679 insns (limit 1000000) max_states_per_insn 6 total_states 86 peak_states 63 mark_read 25

-- END PROG LOAD LOG --
libscap: bpf_load_program() event=raw_tracepoint/filler/proc_startupdate: Operation not permitted (1)
```

# fedora-builder build-kernel-module

Msg:
```
non-zero return code
```
Err:
```
make[5]: *** /lib/modules/5.14.16/build: No such file or directory.  Stop.
make[4]: *** [Makefile:16: all] Error 2
make[3]: *** [driver/CMakeFiles/driver.dir/build.make:70: driver/CMakeFiles/driver] Error 2
make[2]: *** [CMakeFiles/Makefile2:595: driver/CMakeFiles/driver.dir/all] Error 2
make[1]: *** [CMakeFiles/Makefile2:602: driver/CMakeFiles/driver.dir/rule] Error 2
make: *** [Makefile:273: driver] Error 2
```

# fedora-builder scap-open-and-kernel-module

Msg:
```
[Errno 2] No such file or directory: b'/tmp/scap-open'
```
Err:
```

```

# fedora-builder build-bpf-probe

Msg:
```
non-zero return code
```
Err:
```
expr: syntax error: unexpected argument ‘1’
make[5]: *** /lib/modules/5.14.16/build: No such file or directory.  Stop.
make[4]: *** [Makefile:38: all] Error 2
make[3]: *** [driver/bpf/CMakeFiles/bpf.dir/build.make:70: driver/bpf/CMakeFiles/bpf] Error 2
make[2]: *** [CMakeFiles/Makefile2:647: driver/bpf/CMakeFiles/bpf.dir/all] Error 2
make[1]: *** [CMakeFiles/Makefile2:654: driver/bpf/CMakeFiles/bpf.dir/rule] Error 2
make: *** [Makefile:299: bpf] Error 2
```

# fedora-builder scap-open-and-bpf-probe

Msg:
```
[Errno 2] No such file or directory: b'/tmp/scap-open'
```
Err:
```

```

# oraclelinux-5.4 scap-open-and-modern-probe

Msg:
```
non-zero return code
```
Err:
```
libpman: tracing program type is not supported (errno: 22 | message: Invalid argument)
 (1)
```

