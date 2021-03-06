# Post Installation

The post install section will walk users though the required actions following the base installation. By far, `postinstall` represents the lions share of the setup and will perform the following tasks:

- VC/C++ Runtime installation
- Git-SCM installation
- VS Code installation
- Qt configuration (default of full)
- Initial MSYS2 Setup

This process can take from an hour or so to many hours depending on your system resources and internet speed. 

!!! note
    As of this writing `(3/6/2021)`, the Qt Online Installer has a circular dependency on MS VC Redit dll's. They are not present in a new Win-10 image, yet the Qt Online Installer requires them to run. As such, the `postinstall` script will download and install them for you prior to running the `Qt Online Installer`.

## JTSDK64 Tools Setup

After completing the base installation, use the desktop icon or Win-10 search bar to find and open `JTSDK64-Tools-Setup`. Upon initial opening, you should see the following screen. At the prompt, just hit enter.

<figure>
  <img src="../images/3-Run-Setup-2.PNG" width=auto />
  <figcaption>JTSDK64 Setup Initial Screen</figcaption>
</figure>

Once you are at the Post Install Setup Selection screen you will see the current environment. At the prompt, type: **`postinstall`**

<figure>
  <img src="../images/3-Run-Setup-3.PNG" width=auto />
  <figcaption>JTSDK64 Setup Initial Screen</figcaption>
</figure>

## Tool Selection

For this example, we will be using a minimal install configuration for building `WSJT-X`. 

Set the following defaults when asked:

- VC Redist set tp `Y`
- Omnirig set to `Y`
- Git-SCM set tp `Y`
- Default Qt set tp `D`
- MSYS2 Setup set to `Y`
- VS Code set to `Y`

!!! note
    VS Code is optional. However, it is a highly capable editor that performs many tasks including integrated Bash, PowerShell and Windows CMD terminals. It's up to the user, but, the development team recommends its use.

<figure>
  <img src="../images/3-Run-Setup-4.PNG" width=auto />
  <figcaption>JTSDK64 Setup Tools Selection</figcaption>
</figure>

## VC Redist Install

The first action will be to download and install MS VS Redist. This is mostly automated, but you will be prompted to allow installation by the normal Windows UAC prompts.

<figure>
  <img src="../images/3-Run-Setup-5.PNG" width=auto />
  <figcaption>VS Redist Installation</figcaption>
</figure>

## Install Omnirig

Next up is Omnirig. If the download is successful (sometimes the download fails, so be prepared) you will see the install wizard appear. Use the defaults and progress through all screens using the `Next` button.

<figure>
  <img src="../images/3-Run-Setup-6.PNG" width=auto />
  <figcaption>Omnirig Installation</figcaption>
</figure>

Omnirig Install Prompt.

<figure>
  <img src="../images/3-Run-Setup-7.PNG" width=auto />
  <figcaption>Omnirig Installation Prompt</figcaption>
</figure>

## Install VS Code

The VS Code installer should appear, and again you should be prompted with the normal Windows UAC prompts.

<figure>
  <img src="../images/3-Run-Setup-8.PNG" width=auto />
  <figcaption>VS Code Installation</figcaption>
</figure>


## Qt Installation

The `Qt` installation can be a rather lengthy process. The default selection installs all that is needed for a base `WSJT-X` build. When the UX appears, you will need the following:

- Your Qt account username/email address
- Your Qt account Password

<figure>
  <img src="../images/3-Run-Setup-9.PNG" width=auto />
  <figcaption>Qt Account Screen</figcaption>
</figure>

Open Source Obligations. Have a read though them if this is the first time using Qt. Additional, ensure you check the box stating you are an individual user, not a company.

<figure>
  <img src="../images/3-Run-Setup-10.PNG" width=auto />
  <figcaption>Qt Open Source Obligations</figcaption>
</figure>

Sending usage stats. While this is optional, it helps the `Qt` Developers find and resolve high impacts bugs. Participation is up to the end users, but, it seems a fitting thing to do for the Open Source Community.

<figure>
  <img src="../images/3-Run-Setup-11.PNG" width=auto />
  <figcaption>Qt Contribute to Development</figcaption>
</figure>

Component selection and agreements are pre-selected for you. All that is left at this point is to sit back and wait for the download an installation to progress.

!!! note
    The only way to cancel the UX at this point (due to scripted) is to use the Windows Task Manager to kill the process (if needed).

<figure>
  <img src="../images/3-Run-Setup-12.PNG" width=auto />
  <figcaption>Qt Download and Installation</figcaption>
</figure>

Upon completion, you will see (in the Powershell Environment) what components were installed.

<figure>
  <img src="../images/3-Run-Setup-12a.PNG" width=auto />
  <figcaption>Qt Installed Components Message</figcaption>
</figure>

## Close JTSDK64 Tools Setup

At this point, if there were no errors or problems with the automated installers, you are ready to setup MSYS2. This will all be performed in the standard `JTSDK64-Tools` environment **not** `JTSDK64-Tools-Setup`.

- Close `JTSDK64-Tools-Setup` environment.
- Proceed to the next section.
