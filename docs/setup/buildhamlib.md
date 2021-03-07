# Build Hamlib

If all has gone without error to this point, you are ready to build `Hamlib` from a git repository. At present, the preferred repository is the Hamlib Master. If this changes for WSJT-X, you can always adjust it with menu option (**8**).

Using the `MSYS2` Menu, select option (**8**), followed by selecting (**1**) to set the Mater Repository, then (**e**) to return to the main menu.

!!! note
    The default selection is set to `hlmaster` during the base installation. This step is to illustrate how to change the repository if and when it is needed.

<figure>
  <img src="../images/4-MSYS2-6.PNG" width=auto />
  <figcaption>Select Hamlib Repository</figcaption>
</figure>


After setting the repository, use the menu option (**5**) to commence the `Hamlib` build. If all goes as expected, you should see results similar to the following:


During the Build:

<figure>
  <img src="../images/5-Build-Hamlib-2.PNG" width=auto />
  <figcaption>Hamlib Build Progress</figcaption>
</figure>

Completed Build:

<figure>
  <img src="../images/5-Build-Hamlib-3.PNG" width=auto />
  <figcaption>Hamlib Build Results</figcaption>
</figure>

This concludes building Hamlib. You can close `MSYS2`, and move back to the `JTSDK64-Tool` environment for the next step.