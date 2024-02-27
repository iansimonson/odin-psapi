# odin-psapi
Windows [PSAPI](https://learn.microsoft.com/en-us/windows/win32/api/_psapi/) bindings for Odin

**should** support both PSAPI_VERSION 1 and 2 (default 2)

Most of these can just be brought into `core:sys/windows` in the future as psapi.lib is deprecated and all the functions were moved into kernel32.lib

## Importing odin-psapi

You can just drop the `odin-psapi` directory into your
project (or shared) and import via `import psapi "odin-psapi"` (or `import psapi "shared:odin-psapi"`)

If you want to keep the entire git repo then just import via `import "odin-psapi/odin-psapi"`