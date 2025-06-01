# ProjectAcousticsArchive

An **Unofficial Archive** for [Project Acoustics](https://github.com/microsoft/ProjectAcoustics) and its processors.  
I'll try to keep it updated, but no promises.

---

## 📝 TODO
- [ ] **Create a Demo Level**
- [ ] **Add Instructions for Usage**

---

## 🐛 Issues / Bugfixes

### 🔴 Issue: Python Plugin Error
If you see the error message:

> **"python must be installed"**

(while the Python plugin is correctly installed), and an error in the logs like this:

```
[2025.02.13-22.58.58:436][  0] LogPython: Display: Running start-up script C:/Projects/PA_Demo/Plugins/ProjectAcousticsNative/Content/Python/init_unreal.py... started...
[2025.02.13-22.58.58:587][  0] LogSourceControl: Uncontrolled asset enumeration finished in 0.190773 seconds (Found 7711 uncontrolled assets)
[2025.02.13-22.58.59:337][  0] LogPython: Error: System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. See http://go.microsoft.com/fwlink/?LinkId=155569 for more information.
[2025.02.13-22.58.59:337][  0] LogPython: Error: The above exception was the direct cause of the following exception:
[2025.02.13-22.58.59:337][  0] LogPython: Error: Traceback (most recent call last):
```

---

### ✅ Fix
1. Open the file:
   ```
   C:\Windows\Microsoft.NET\Framework64\[your .NET version, e.g. 4.0.x]\Config\machine.config
   ```

2. Find this line:
   ```xml
   <runtime/>
   ```

3. Replace it with:
   ```xml
   <runtime>
       <loadFromRemoteSources enabled="true"/>
   </runtime>
   ```

This should resolve the issue with the sandboxed assembly error in Unreal Engine.
