# MSYS2 Setup

In this section, the following tasks will be performed in the `MSYS2 Terminal` launched from within `JTSDK64-Tools Environment`. Before proceeding, ensure you have closed `JTSDK64-Tools-Setup` and any `MSYS2` terminals before opening the `JTSDK64-Tools` Environment.

!!! caution
    With MSYS2, **`Do Not`** use the `RED - X` to close the terminal. Get in a habit of typing **`exit`** from within the terminal itself to properly close the session as not doing so can cause stranded threads and other anomalies in the environment.

Tasks to perform:

- Open `JTSDK64-Tools Environment`
- Launch `MSYS2` terminal
- Update MSYS2 via menu option (2)
- Install Hamlib Dependencies via menu option (3)
- Update the MSYS2 Keyring via the menu option (4)
- Close and Re-Open MSYS2 from `JTSDK64-Tools Environment`
- Build Hamlib Static assemblies via menu option (5)


## Open JTSDK64-Tools

From the Desktop Link or Windows Search menu, find and launch the `JTSDK54-Tools` environment, then launch `MSYS2` from the command-line.

```powershell
# In the JTSDK64-Tools Powershell environment, type:

msys2

```
Upon opening `MSYS2` ensure you have a Qt version listed at the top of the terminal. If you do not, you need investigate why it is not present before continuing.

<figure>
  <img src="../images/4-MSYS2-0.PNG" width=auto />
  <figcaption>MSYS2 Base Terminal</figcaption>
</figure>

## Update MSYS2 Packages

From the main MSYS2 terminal, launch the menu and update the packaging using menu option (2)

<figure>
  <img src="../images/4-MSYS2-1.PNG" width=auto />
  <figcaption>MSYS2 Main Menu</figcaption>
</figure>

At the completion of the update, exit the menu system (type `exit` from the MSYS2 terminal) and re-open `MSYS2` from `JTSDK54-Tools` again.

!!! note
    Over time, there may be more package updates than what is shown in this document and your results may not always match the example presented here. This is normal, and to a degree, expected.

<figure>
  <img src="../images/4-MSYS2-2.PNG" width=auto />
  <figcaption>MSYS2 Package update completion</figcaption>
</figure>


## Install Hamlib Dependencies

After updating `MSYS2` packages, it's time to install `Hamlib Dependencies`.

From the `MSYS2 Menu`, select option (3). At the completion of this step, there is **`no need`** to close and re-open MSYS2 again, just proceed to the next step.

<figure>
  <img src="../images/4-MSYS2-4.PNG" width=auto />
  <figcaption>Install Hamlib Dependencies</figcaption>
</figure>


## Update MSYS2 Keyring

While it's debatable, the keyring update is being performed after the initial `Hamlib` dependency installation. After running this step, `close and re-open` MSYS2 from the `JTSDK64-Tools` environment.

From the `MSYS2` menu, select option (4) top update the keyring.

<figure>
  <img src="../images/4-MSYS2-5.PNG" width=auto />
  <figcaption>Update MSYS2 Keyring</figcaption>
</figure>


This concludes the MSYS2 update portion. Close and re-open `MSYS2`, and proceed to the next step.