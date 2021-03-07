# Build Configuration

In this section you will set the default variables used to compile various elements in the remainder of the setup process. There will be a detailed review of each item listed in `Versions.ini`, but for now, we will only be looking at a few key parameters. 

!!! note
    At present, setting the configuration variables is a manual process to a degree. In future releases this will be a more elegant solution.

## Version File Update

Now is a good time to set several variables that will be used when building `Hamlib`, `Deploying Boost` and compiling `WSJT-X`. The options of immediate concern are:

- cleanfirst
- reconfigure
- autorun
- cpuusage

To set these variables, open the the `JTSDK64-Tools`, then using `VS Code` issue the following command:

```powershell
# In JTSDK64-Tools, at the prompt, type: 

code .\config\Versions.ini

```

This will open the `Version.ini` file in VS Code editor. Set the variables as indicated below.

<figure>
  <img src="../images/3-Run-Setup-15.PNG" width=auto />
  <figcaption>JTSDK64-Tools Environment</figcaption>
</figure>

!!! note
    What one uses for CPU count is entirely up to them. Just know, the more threads you use, the faster build times will be. Most are using a Virtual Machine, and in doing so, they use all the cores they've allocated in the VM. The options are `All`, `Half`, or `Solo`. For the remainder of options, there is only `Yes` or `No` available.


Set the following options:

- cleanfirst=Yes
- reconfigure=Yes
- autorun=No
- cpuusage=All

Save and exit VS Code. 

After saving the file, `close` and `re-open` the JTSDK64-Tools Environment. Proceed to the MSYS2 setup section.
