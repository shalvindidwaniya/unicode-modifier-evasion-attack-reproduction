Explanation Regarding Public Research Infrastructure Compatibility

Thank you for evaluating our artifact. We would like to explain why our submission may not be directly compatible with the standard Linux-based public research infrastructures (such as SPHERE, Chameleon, CloudLab, and FABRIC).

Our artifact is built around pre-compiled Windows executables (`analyzer.exe` and `checker.exe`). The primary constraints are:

1.  **Operating System:** The binaries were compiled for and require the Microsoft Windows operating system (specifically, Windows 10 or compatible versions) to execute. We understand that the standard research infrastructures predominantly offer Linux environments, making direct execution there unfortunately not possible.

2.  **Build Environment Dependencies:** The software was developed and compiled using Microsoft Visual Studio 2013. This introduces dependencies on specific versions of the Microsoft Visual C++ runtime libraries, which are native to the Windows ecosystem and are not available on Linux systems.

3.  **Architecture:** The software is compiled for the x86-64 architecture.

To ensure a smooth evaluation process despite these constraints, we have prepared a complete package to be run in a Windows environment. 

We appreciate your understanding and flexibility in accommodating these requirements.