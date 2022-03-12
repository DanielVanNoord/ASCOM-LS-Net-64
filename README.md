## TelescopeSimulator-Core

This is an experimental port of the ASCOM .Net Telescope Simulator to 64bit .Net 6.0. It depends on the (also experimental) ASCOM.Core libraries which are included as a Sub Module and also can be found here: https://github.com/DanielVanNoord/ASCOM.Core. 

This requires .Net Core 6.0 release to build.

This project uses Git submodules. Be sure to clone it recursively and init the project.

It is best to register the server directly using the -register argument. All the server registration, including elevation, should be working. Passing the -register argument from the Visual Studio project debug arguments is currently not working as the server is run within the dotnet.exe tool when started from the debugger rather then standalone. You can attach to it after it is started to debug the registration.

## Known issues:

.Net 6.0 should now support dynamic dispatch (https://github.com/dotnet/runtime/pull/33060). This fix seems to work, I tested it in both Powershell and Python with great success. 

The Telescope simulator currently uses a virtualized version of ASCOM Profile that does not save settings across resets. Likewise the logger logs to the console. These will be switched to cross platform libraries moving forward.