# Android Native Tools

Provide some useful tools for Android developers. 个别工具需要root权限.

支持将工具打包成Magisk模块使用

## procmem

```
Usage: procmem [ -w | -W ] [ -p | -m ] [ -h ] pid
    -w  Displays statistics for the working set only.
    -W  Resets the working set of the process.
    -p  Sort by PSS.
    -m  Sort by mapping order (as read from /proc).
    -h  Hide maps with no RSS.
```

## procrank

Android 7中提取的procrank源码

```
Usage: procrank [ -W ] [ -v | -r | -p | -u | -s | -h ]
    -v  Sort by VSS.
    -r  Sort by RSS.
    -p  Sort by PSS.
    -u  Sort by USS.
    -s  Sort by swap.
        (Default sort order is PSS.)
    -R  Reverse sort order (default is descending).
    -c  Only show cached (storage backed) pages
    -C  Only show non-cached (ram/swap backed) pages
    -k  Only show pages collapsed by KSM
    -w  Display statistics for working set only.
    -W  Reset working set of all processes.
    -h  Display this help screen.
```

## procrank-9

Android 9中提取的procrank源码用法与procrank一致
