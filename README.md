# Embedded_System_Security
Embedded System Security notes
Embedded System Secuirty

GCC offers several security features that you can enable to enhance the security of your compiled programs. Here are some key options:

Stack Protection:

  -fstack-protector: Adds checks to detect stack buffer overflows.
  
  -fstack-protector-strong: Protects more functions, including those with local variables that have their addresses taken.
  
  -fstack-protector-all: Protects all functions1.

Fortify Source:

  -D_FORTIFY_SOURCE=2: Adds checks for buffer overflows in functions like sprintf and strcpy1.
  
Position Independent Executable (PIE):

  -fPIE and -pie: Generates position-independent code, which is useful for Address Space Layout Randomization (ASLR)1.
  
Control Flow Integrity (CFI):

  -fcf-protection: Adds control flow integrity checks to prevent certain types of attacks1.
  
Stack Clash Protection:

  -fstack-clash-protection: Protects against stack clash attacks1.
  
Automatic Variable Initialization:

  -ftrivial-auto-var-init=zero: Initializes stack variables to zero to prevent the use of uninitialized memory2.
  
Relocation Read-Only (RELRO):

  -Wl,-z,relro and -Wl,-z,now: Marks certain sections of the program as read-only after they are initialized1.
  
No Executable Stack:

  -Wl,-z,noexecstack: Ensures the stack is not executable1.
  
These options can significantly enhance the security of your applications by adding various checks and protections against common vulnerabilities.


