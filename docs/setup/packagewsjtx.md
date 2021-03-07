# Package WSJT-X

The final test for the setup process is to functionally test a packge build for `WSJT-X`. Using the packge option will exercise most of the critical components of the tool chain against a default configuration.

# JTBuild Package

For this step we use `jtbuild` to kick off the the process. 

```powershell
# At the default prompt in `JTSDK64-Tools, type: 

jtbuild package

```

<figure>
  <img src="../images/6-Build-WSJTX-1.PNG" width=auto />
  <figcaption>JTBUILD Package Invocation</figcaption>
</figure>


## Competed Package

The output from a sucessful should should resemble the following:

<figure>
  <img src="../images/6-Build-WSJTX-2.PNG" width=auto />
  <figcaption>Sucessful Package Build</figcaption>
</figure>

# WSJT-X Installed

The last, and most important step is run the package installer, and verify that `WSJT-X` is functional.

<figure>
  <img src="../images/6-Build-WSJTX-3.PNG" width=auto />
  <figcaption>WSJT-X Running after Install</figcaption>
</figure>

This concludes the setup and test sections for `JTSDK64-Tools`.