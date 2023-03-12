# cs_BOFs

Random BOFs that I may or may not use in the future. 


## Find-DLLProxying-Canidate

Here's a BOF code that will search for processes that are calling a DLL that does not exist on the system, which can indicate a potential candidate for DLL hijacking:

This code uses the Win32 API functions CreateToolhelp32Snapshot and Process32First/Process32Next to iterate over all processes on the system. For each process, it uses CreateToolhelp32Snapshot and Module32First/Module32Next to iterate over all loaded modules (DLLs) of the process. If the path of a module ends with ".dll" and its file attributes indicate that it does not exist, the BOF will print a message to the Beacon console indicating that the DLL is suspicious and may be a candidate for DLL hijacking.

Note that not all DLLs that are loaded by a process but do not exist on the system are necessarily candidates for DLL hijacking, as some may be legitimate system or application files that are temporarily loaded into memory. This BOF is intended to help identify potential candidates for further investigation, but further analysis is required to determine whether a DLL is actually vulnerable to DLL hijacking.


## Find-Passwords

Here's a simple BOF code that searches for all files in the Windows file system that have the string "password" in their name and prints their full path to the Beacon console:

This code uses the Win32 API function FindFirstFileA to find the first file in the Windows file system and FindNextFileA to iterate over all files in the system. It then checks if each file's name contains the string "password" using the strstr function and prints the full path of any matching files to the Beacon console using BeaconPrintf. Finally, it closes the file handle and prints a message indicating that the search is complete. Note that this BOF only searches the root directory of the C:\ drive, but you can modify the search pattern to include other directories or drives as needed.
