# ProjectAcousticsArchive

An Un-Official Archive for https://github.com/microsoft/ProjectAcoustics and it's processors, this project has the occasional updates... support is best effort...

[TODO] Instructions for usage

[Issues/Bugfixes]

ISSUE: If you see "python must be installed" (and you have the python plugin installed properly) when opening the probes tab in the editor UI, and an error in the logs similar to the below...

[2025.02.13-22.58.58:436][  0]LogPython: Display: Running start-up script C:/Projects/PA_Demo/Plugins/ProjectAcousticsNative/Content/Python/init_unreal.py... started...
[2025.02.13-22.58.58:587][  0]LogSourceControl: Uncontrolled asset enumeration finished in 0.190773 seconds (Found 7711 uncontrolled assets)
[2025.02.13-22.58.59:337][  0]LogPython: Error: System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. See http://go.microsoft.com/fwlink/?LinkId=155569 for more information.
[2025.02.13-22.58.59:337][  0]LogPython: Error: The above exception was the direct cause of the following exception:
[2025.02.13-22.58.59:337][  0]LogPython: Error: Traceback (most recent call last):

FIX:
1) goto C:\Windows\Microsoft.NET\Framework64\\[version, probably 4.0(something)]\Config\machine.config

2) find and replace

\<runtime/>

with

\<runtime>\
	\<loadFromRemoteSources enabled="true"/>\
\</runtime>
