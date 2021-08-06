```asm
format ELF
public _start
section '.data' writeable
  msg db "The most important vulnerability, the person sitting on the PC.", 0xA, 0x0
  siz = $-msg
section '.text' executable
_start:
  mov eax, 4
  mov ebx, 1
  mov ecx, msg
  mov edx, siz
  int 0x80
exit:
  mov eax, 1
  xor ebx, ebx
  int 0x80```
