
Visual Studio / UCRT
====================

By default, Visual Studio (since 2015) uses the Visual C++ runtime
(`vcruntimeXXX.dll`) included in the latest "Visual C++ Redistributable", and
the UCRT dlls. The compiled program needs these DLLs to run.

To eliminate the dependency on the redistributable part, while not increasing
the size of the executable too much, it is possible to statically link with the
VC++ runtime (smallest), and to dynamically link against the UCRT (biggest).

The generated executables require the UCRT dlls to run (included in Windows 10
or installed by the cumulative updates in older versions).

The executable size is around 26-31 KB.

- Open the `msvc\ucrt\superUser.sln` solution with Visual Studio.
- In the toolbar, choose the _Release_ configuration.
- Select the platform (_x64_, _x86_, _ARM_ or _ARM64_).
- Build the solution (menu _Build > Build Solution_, or press _Ctrl+Shift+B_).

This creates the executables in the solution directory (`msvc\ucrt`).
