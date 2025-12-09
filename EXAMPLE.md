This is an example of coding on C*:

```
[INIT]
INCLUDE IOS
INCLUDE RUBY
INCLUDE VAR
INCLUDE MATH
IF ($SYSTEM == _w11) 
\- INCLUDE WINDOWS
ELIF (self == _w10)
\- INCLUDE WINDOWS
\- INCLUDE WINDOWS.LEGACY
ELIF (self == linux)
\- INCLUDE LINUX
\- MODULE C*BASH
ELIF (self == macos)
\- INCLUDE MACOS
\- MODULE C*SWIFT
ENDIF/
/
[DEF]
DEFINE VARIABLE.DWORD ERR 0x1
DEFINE VARIABLE.DWORD RET 0x0
DEFINE RUBY.KEY.COLON-SLASH = TRUE
DEFINE STRING.STD MESSAGE "HELLO WORLD ON C-Char !"
/

[LOOSE]
USING STD_25

[MAIN]
\- [args=true]
\- guiflags (nullptr)
[SOURCE]
  console.out $MESSAGE;
  string.std message = console.in(getline)
  console.out message;
\end
