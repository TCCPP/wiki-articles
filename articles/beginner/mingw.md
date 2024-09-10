<!-- alias mingw, install-mingw -->
<!-- title -->
# How to Install MinGW-w64 
1. Download and run the [MSYS2](https://www.msys2.org/#installation) installer with the default options.
2. After installation, a terminal for the [UCRT64 environment](https://www.msys2.org/docs/environments/) will launch. 
3. In the terminal, run: `pacman -S mingw-w64-ucrt-x86_64-gcc mingw-w64-ucrt-x86_64-gdb`.
4. Open the [Start menu](https://support.microsoft.com/en-us/windows/open-the-start-menu-4ed57ad7-ed1f-3cc9-c9e4-f329822f5aeb) and search for `cmd.exe`.
5. Right-click on **Command Prompt** and select **Run as administrator**.
6. Run: `setx PATH "%PATH%;C:\msys64\ucrt64\bin;"`.
7. Restart your session or PC to make `gcc` and `gdb` commands available.

## See also
- [MSYS2 Package Index](https://packages.msys2.org/queue)
- [Updating MSYS2](https://www.msys2.org/docs/updating/)
