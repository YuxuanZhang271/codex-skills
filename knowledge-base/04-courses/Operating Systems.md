---
title: "Operating Systems"
type: course
status: active
created: "2026-05-07"
updated: "2026-05-07"
research_area: operating_systems
tags:
  - course/operating-systems
  - computer-systems
  - interview-prep
---

# Operating Systems

## Purpose

This note summarizes operating-system concepts in English for academic and interview-oriented study. It is structured as a learning guide, with Linux-oriented systems knowledge preserved as the practical focus.

## Reference

- [Operating systems visual explanation reference](https://www.xiaolincoding.com/os/)

## High-Level Summary

Operating systems should be studied as a practical systems-engineering topic rather than only a university theory course. The focus here is on the parts that developers frequently meet in debugging, performance tuning, Linux work, backend interviews, and server-side engineering.

The central idea is that an operating system sits between application programs and hardware. It hides hardware complexity, provides stable abstractions, allocates shared resources, and enforces isolation. A useful learning pattern is:

1. Start from a concrete developer-facing question.
2. Explain the hardware or kernel mechanism behind it.
3. Show the performance or reliability tradeoff.
4. Connect the mechanism to interview questions and real engineering scenarios.

## Learning Position

This note is best treated as a **visual review and conceptual bridge**, not as a complete textbook replacement.

Use it for:

- Building an operating-system knowledge map.
- Understanding common interview topics with less friction.
- Connecting abstract OS terms to practical Linux and backend engineering examples.
- Reviewing CPU, memory, process, file-system, device, and network I/O concepts.

Do not use it alone for:

- Formal proofs.
- Full kernel implementation details.
- Complete OS course coverage.
- Linux source-code-level study.

## Recommended Learning Order

For a serious academic path, study the most connected OS modules first:

1. **Memory management**: virtual memory, segmentation, paging, page tables, TLB, Linux memory layout, page cache, memory pressure.
2. **Process and thread management**: process states, process control blocks, context switching, threads, synchronization, deadlock, locks.
3. **File systems**: inode, dentry, block layout, virtual file system, links, buffering, direct I/O, synchronous and asynchronous I/O.
4. **Device and I/O management**: device controllers, drivers, interrupts, DMA, block layer, keyboard input path.
5. **Network systems**: zero-copy, PageCache, sendfile, socket model, I/O multiplexing, epoll, Reactor and Proactor patterns.
6. **Hardware background**: CPU execution, cache, cache consistency, soft interrupts, floating-point representation.
7. **Linux commands**: network performance inspection and log analysis.

## Topic Map

| Area | What To Learn | Core Questions |
| --- | --- | --- |
| Hardware and CPU | Turing-machine intuition, von Neumann model, CPU registers, buses, instruction execution, cache, soft interrupts, floating point | How does source code become CPU execution? Why do cache and locality affect performance? |
| OS structure | Kernel roles, Linux process model, Linux file abstraction, Linux device and I/O interfaces | What does the kernel abstract, isolate, and schedule? |
| Memory management | Virtual memory, physical memory, segmentation, paging, multi-level page tables, TLB, malloc, page cache, OOM behavior | Why does each process get its own address space? What happens when memory is insufficient? |
| Process management | Process lifecycle, PCB, context switching, threads, IPC, synchronization, deadlock, pessimistic and optimistic locks | How does the OS multiplex CPU time and isolate running programs? |
| Scheduling | CPU scheduling, page replacement, disk scheduling | What tradeoffs do scheduling algorithms optimize? |
| File systems | inode, dentry, VFS, file layout, free-space management, links, buffered and direct I/O | How does the OS turn persistent disk blocks into files and directories? |
| Device management | Device controllers, I/O control methods, drivers, interrupts, block layer | How does the OS standardize many different hardware devices? |
| Network systems | Socket model, zero-copy, DMA, PageCache, select, poll, epoll, Reactor, Proactor | How do high-performance servers reduce copying, blocking, and context switching? |
| Linux commands | Network metrics, log-based PV/UV analysis | How can OS knowledge be checked in real Linux systems? |

## Key Explanations

### 1. CPU Execution

The CPU section builds from the idea that a computer repeatedly reads instructions and data, interprets instructions, performs operations, and writes results. The developer-level takeaways are:

- A program is not "run" directly from source code; it becomes instructions and data placed in memory.
- CPU registers are necessary because main memory is far slower than CPU execution.
- Program counters and instruction registers explain sequential instruction execution and control flow.
- Bus width, CPU word size, and address width constrain how much data or memory can be directly handled.
- Cache locality matters because the CPU can waste large amounts of time waiting for memory.

### 2. Virtual Memory

Virtual memory is the organizing abstraction for modern process isolation. Each process sees its own virtual address space, while the OS and MMU translate virtual addresses to physical addresses.

Main points:

- Direct physical addressing would make multiple programs overwrite each other.
- Virtual address spaces isolate processes and make memory management transparent to applications.
- Paging is the dominant practical mechanism because it manages fixed-size pages and avoids many segmentation problems.
- Multi-level page tables reduce page-table memory overhead.
- The TLB caches recent virtual-to-physical translations, which makes address translation fast in the common case.
- Process context switches can invalidate address-translation locality, which partly explains why process switches are more expensive than thread switches.

### 3. Processes and Threads

A process is a running program with its own address space and kernel-managed execution state. A thread is a lighter execution unit inside a process.

Main points:

- Processes let the OS multiplex CPU time across many running programs.
- Context switching requires saving and restoring execution state.
- Threads share much of the process resource context, so thread switching is typically cheaper than process switching.
- Concurrency introduces shared-state problems, so synchronization mechanisms are needed.
- Deadlock should be understood through resource holding, waiting, circular dependency, and lack of preemption.
- Locks are tradeoffs: pessimistic locks protect by excluding concurrent access, while optimistic locks assume conflicts are rare and validate updates later.

### 4. Scheduling

Scheduling is the OS policy layer for choosing what should run or be replaced next.

Scheduling can be grouped into three families:

- **CPU scheduling**: FCFS, shortest-job-first, highest-response-ratio-next, round-robin, priority scheduling, multilevel feedback queues.
- **Page replacement**: what physical page should be evicted when memory is full.
- **Disk scheduling**: how disk requests should be ordered to reduce seek overhead.

The important academic point is not memorizing algorithm names. The important point is learning what each algorithm optimizes and what unfairness or overhead it introduces.

### 5. File Systems

The file-system section explains how persistent storage becomes a usable file abstraction.

Main points:

- Linux treats many objects as files, including regular files, directories, pipes, sockets, and devices.
- An inode stores file metadata and block location information.
- A dentry maps names and directory hierarchy to inodes and is cached by the kernel.
- File systems use blocks as larger logical units over disk sectors to improve efficiency.
- Virtual File System provides a common interface over different file-system implementations.
- Buffered I/O uses kernel memory to reduce disk access frequency, while direct I/O bypasses parts of that cache path.

### 6. Device Management

Device management explains how the OS controls heterogeneous hardware through common interfaces.

Main points:

- Device controllers expose registers for commands, status, and data.
- The CPU should not directly know every detail of every physical device.
- Drivers translate OS-level operations into device-specific control.
- Interrupts let devices notify the CPU when work is ready or complete.
- DMA moves bulk data between devices and memory without making the CPU copy every byte.

### 7. Network I/O and Zero-Copy

The network-system chapters connect OS internals to backend server performance.

Main points:

- Traditional file transfer can involve multiple user-kernel transitions and memory copies.
- DMA reduces CPU involvement in data movement.
- `sendfile` and zero-copy paths reduce unnecessary copying between kernel buffers and socket buffers.
- PageCache improves repeated file reads by caching disk data in memory.
- Socket programming starts with `socket`, `bind`, `listen`, `accept`, `connect`, `read`, and `write`.
- The C10K problem is not only a hardware capacity problem; it is also an I/O model problem.
- `select`, `poll`, and `epoll` exist to let one process monitor many file descriptors efficiently.
- Reactor and Proactor are design patterns for structuring high-performance network servers around event readiness or completion.

## Study Strategy

### First Pass: Build The Map

Read the introduction and the chapter titles first. The goal is to understand the dependency graph:

- Memory management supports process isolation.
- Process and thread switching depends on memory context and CPU state.
- File systems and network systems both rely on kernel buffers and I/O abstractions.
- Device management explains interrupts and DMA, which later reappear in zero-copy and high-performance I/O.

### Second Pass: Study One Mechanism At A Time

For each topic, write down:

- What problem does this mechanism solve?
- What abstraction does the OS expose upward?
- What hardware detail does it hide downward?
- What performance cost does it introduce?
- What failure mode or interview question naturally follows?

### Third Pass: Connect To Linux Practice

For academic and engineering usefulness, pair each conceptual topic with a Linux observation:

- Memory: `free`, `vmstat`, `/proc/meminfo`, `pmap`.
- Processes and threads: `ps`, `top`, `pidstat`, `/proc/<pid>/`.
- Files: `ls -li`, `stat`, `lsof`, `df`, `du`.
- Network: `ss`, `netstat`, `sar`, `tcpdump`, `ethtool`.
- Logs: shell pipelines for PV/UV analysis.

### Fourth Pass: Interview Compression

After studying, compress each module into a short answer:

- Definition.
- Mechanism.
- Tradeoff.
- Example.
- Common pitfall.

This format is useful for interviews because it avoids isolated memorization and shows systems reasoning.

## Personal Academic Takeaways

- Operating systems should be studied as a set of abstractions that control scarce resources: CPU time, memory, storage, devices, and network I/O.
- Many OS concepts share the same design pattern: hide lower-level heterogeneity and expose a uniform interface upward.
- Virtualization is a recurring idea: virtual memory, virtual file systems, process abstraction, file descriptors, and network sockets all make difficult hardware details manageable.
- Performance problems often come from the boundaries: user/kernel transitions, context switches, cache misses, page faults, copying, blocking I/O, and lock contention.
- Good OS understanding helps with backend systems, robotics runtime performance, simulation infrastructure, distributed systems, and debugging.

## Links To My Vault

- [[02-concepts/Embodied AI]]
- [[02-concepts/Robotic Manipulation]]
- [[04-courses/Courses Index|Courses Index]]
