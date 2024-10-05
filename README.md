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
  The compiler replaces standard functions like memcpy, strcpy, sprintf, and others with safer versions that include runtime checks. These checks help detect buffer overflows and other memory-related errors

  
Position Independent Executable (PIE):

  -fPIE and -pie: Generates position-independent code, which is useful for Address Space Layout Randomization (ASLR)1.
  
Control Flow Integrity (CFI):

  -fcf-protection: Adds control flow integrity checks to prevent certain types of attacks1.
  
  This helps prevent certain types of attacks, such as return-oriented programming (ROP) and jump-oriented programming (JOP), which exploit vulnerabilities in the control flow of a program
  
Stack Clash Protection:

  -fstack-clash-protection: Protects against stack clash attacks.
  When you enable -fstack-clash-protection, the compiler inserts probes into the code to ensure that large stack allocations do not skip over guard pages. This helps to detect and prevent stack clashes by making sure that any large allocation on the stack will trigger a page fault if it tries to overwrite adjacent memory regions.
  
Automatic Variable Initialization:

  -ftrivial-auto-var-init=zero: Initializes stack variables to zero to prevent the use of uninitialized memory.
  
Relocation Read-Only (RELRO):

  -Wl,-z,relro and -Wl,-z,now: Marks certain sections of the program as read-only after they are initialized.
  
Relocation Read-Only (RELRO) is a security feature in GCC that makes certain sections of a binary read-only to prevent exploitation techniques like Global Offset Table (GOT) overwrites. There are two modes of RELRO: partial and full12.

Partial RELRO:

Default Setting: Partial RELRO is enabled by default in GCC.

Protection: It ensures that the GOT is placed before the BSS (Block Started by Symbol) in memory, reducing the risk of buffer overflows on global variables overwriting GOT entries
.
Full RELRO:

Enhanced Protection: Full RELRO makes the entire GOT read-only, preventing GOT overwrite attacks where an attacker could redirect function calls to malicious code.
  
No Executable Stack:

  -Wl,-z,noexecstack: Ensures the stack is not executable.
  When you use this flag, the linker (ld) is instructed to mark the stack as non-executable. This means that any attempt to execute code from the stack will result in a segmentation fault, effectively preventing the execution of injected code.
  
These options can significantly enhance the security of your applications by adding various checks and protections against common vulnerabilities.



