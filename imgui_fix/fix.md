# Pull Request

## Description
Can't load files which its name is encode by gbk

## Change Type
- [x] Bug fix
- [x] Code refactoring

# System Information

- Operating System: Windows 11 (US Version)
- System Architecture: 64-bit
- Compiler: MinGW-w64


## What Happened?

The function `fopen` and `std::ifstream` can't work if the file name has `Chinese` and `Japanese`.(Debug:they will return NULL)

## Bug reproduction
