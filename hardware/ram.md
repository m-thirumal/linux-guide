# RAM

### To check free `RAM` size

    free -m
    free -g
    free -k

OR

    top
### To check/get RAM details

    thirumal@database:~$ cat /proc/meminfo


    MemTotal:       65644732 kB
    MemFree:        59009548 kB
    MemAvailable:   64386820 kB
    Buffers:          531664 kB
    Cached:          5372492 kB
    SwapCached:            0 kB
    Active:          5508996 kB
    Inactive:         466376 kB
    Active(anon):     236100 kB
    Inactive(anon):      272 kB
    Active(file):    5272896 kB
    Inactive(file):   466104 kB
    Unevictable:       26288 kB
    Mlocked:           26288 kB
    SwapTotal:       3903484 kB
    SwapFree:        3903484 kB
    Dirty:               300 kB
    Writeback:             0 kB
    AnonPages:         97504 kB
    Mapped:            96636 kB
    Shmem:            156360 kB
    KReclaimable:     364200 kB
    Slab:             496376 kB
    SReclaimable:     364200 kB
    SUnreclaim:       132176 kB
    KernelStack:        5872 kB
    PageTables:         2816 kB
    NFS_Unstable:          0 kB
    Bounce:                0 kB
    WritebackTmp:          0 kB
    CommitLimit:    36725848 kB
    Committed_AS:     749060 kB
    VmallocTotal:   34359738367 kB
    VmallocUsed:       19008 kB
    VmallocChunk:          0 kB
    Percpu:           103936 kB
    HardwareCorrupted:     0 kB
    AnonHugePages:         0 kB
    ShmemHugePages:        0 kB
    ShmemPmdMapped:        0 kB
    FileHugePages:         0 kB
    FilePmdMapped:         0 kB
    CmaTotal:              0 kB
    CmaFree:               0 kB
    HugePages_Total:       0
    HugePages_Free:        0
    HugePages_Rsvd:        0
    HugePages_Surp:        0
    Hugepagesize:       2048 kB
    Hugetlb:               0 kB
    DirectMap4k:      282432 kB
    DirectMap2M:    66826240 kB

### 