# 5.2 Utilities & Libraries

## Utility Software
- analyzes, configures, optimizes, or maintains the system
- can be called by other software or the OS
- might come with the OS or is installed later

Tasks invole e.g.: encryption, compression, anti-maleware, etc.

### Book example: Hard Disk Formatter and Checker
- formatting (clearing) a disk
- setting up the file system and pointers (table of contents)
- partitioning the disk
- disk repair -> mark 'bad sectors' and recover data

### Hard Disk Defragmenter
- reorganizes files so that data from the same file is closer
    - -> faster to access
- defragmentation means making the data for each file more continuous and less spread out
- becomes impossible if disk is too full

### Backup Utility:
- schedule backups
- create backups only on changes

## Program Libraries
=> contain many little programs that are used as reliable subrotines
- helpful as the coder doesn't have to build everything from scratch

### Linking Libraries to Code:

#### Embed libraryies in source code
- libraries are added to the source code and compiled alongside it
    - -> likely results in many copies of same libraries in memory

#### Dynamic Linked Libraries (DLL)
- The library is separate from the compiled source code
- It's loaded into memory and executed by refferences in the code
- Many programs can use the same library simultaneously
    - + less storage & memory required
    - + easy to update libraries
- programs are dependent on external library
    - -> version errors, etc.

## Exam Style
2, 5, 6

### 2a)
i) 1. Hard Disk formatter utility (✓)
   2. Hard Drive defragmentation utility (defragmenter) (✓)

ii) 1. Used to clean all data of a disk and recreate fresh look-up tables and file structures. ✓
    2. Used to increase the access speed of data on the disk by by resolving any fragmented files. ✓

### b)
i) They are reliable options that replace code the developer would else have to create himself. more efficient, already test ~~When using dynamic linked libraries, memory and storage are also saved.~~

ii) Mathematical / Statistical processing library ✓
Computer graphics calculations? (mb GUI element library)

### 5. a)
A disk formatter is needed to make a disk useful and sometimes even compatible with the system. ✓
> Disk is devided into sectors

- It clears all existing data on the disk ✓
- It creates lookup tables for the data in a way that fits the specific system ✓
- It partitions the disk if needed ✓

### b)
- **Hard Disk Defragmenter**: Bundle files into continuous data and increase speed ✓
- **Disk Repair Utility**: Marks bad sectors and recovers lost data ✓
- **File Compression Utility**: Decreases the file size and therefore increases the free space available on the disk. ✓

### 6. a)
1. He doesn't have to write the code himself. ✓
2. The code is already known to work reliabli ✓

### b)
i) 1. Less memory and storage are used -> explain because the same library is used multiple times
   2. when updating a library it happens for all, as the library is centralized ✓ no need for re-compilation

ii) If the library changes unexpectedly and contains an error, this will also cause an error in the code, even though the source code stayed the same

**Abstraction**: Faulty changes in libraries might result in unforseen errors in the future. ✓