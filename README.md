# odin-psapi
Windows [PSAPI](https://learn.microsoft.com/en-us/windows/win32/api/_psapi/) bindings for Odin

**should** support both PSAPI_VERSION 1 and 2 (default 2)

Most of these can just be brought into `core:sys/windows` in the future as psapi.lib is deprecated and all the functions were moved into kernel32.lib

## Importing odin-psapi

You can just drop the `odin-psapi` directory into your
project (or shared) and import via `import psapi "odin-psapi"` (or `import psapi "shared:odin-psapi"`)

If you want to keep the entire git repo then git clone it into your project and import via `import "odin-psapi/odin-psapi"`

**NOTE:** You will have to import / define some values from `winnt.h` to get the most out of
these bindings. These are not in `core:sys/windows` either at the moment but for example to
use `QueryProcessMemoryInfo` you'll need to call `OpenProcess` with `PROCESS_QUERY_INFORMATION`
and `PROCESS_VM_READ`

Here are some of those values:

```odin
PROCESS_TERMINATE :: 0x0001 
PROCESS_CREATE_THREAD :: 0x0002 
PROCESS_SET_SESSIONID :: 0x0004 
PROCESS_VM_OPERATION :: 0x0008 
PROCESS_VM_READ :: 0x0010 
PROCESS_VM_WRITE :: 0x0020 
PROCESS_DUP_HANDLE :: 0x0040 
PROCESS_CREATE_PROCESS :: 0x0080 
PROCESS_SET_QUOTA :: 0x0100 
PROCESS_SET_INFORMATION :: 0x0200 
PROCESS_QUERY_INFORMATION :: 0x0400 
PROCESS_SUSPEND_RESUME :: 0x0800 
PROCESS_QUERY_LIMITED_INFORMATION :: 0x1000 
PROCESS_SET_LIMITED_INFORMATION :: 0x2000
```
