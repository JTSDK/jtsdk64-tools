# Deploy Boost

There are several options for deploying `Boost`  within the `JTSDK64-Tools` ecosystem. This example will be compiling the library from source so as to test the tool chain and ensure the artifacts are compiled against the same GCC components used to build `WSJT-X`.

!!! warning
    Downloading, extracting, and compiling `Boost` can take a **`very long time`**, in some cases, many hours. Even with high-resource systems and extremely fast internet connections, you are looking at 15 to 20 minutes **minimum**.

Additionally, `JTSDK64-Tools` has the ability to build multiple versions of `Boost`. However, `WSJT-X` needs version `1.74.0` which is the default for the `Boost-Deploy` invocation. Variations of building `Boost` will be covered in the Boost section when it's written.

## Start Deployment

All that is required to kick off the `Boost` build process is to call the `Deploy-Boost` function from the `JTSDK64-Tools` environment

In `JTSDK64-Tools` environment, simply type: **`Deploy-Boost`**

<figure>
  <img src="../images/5-Deploy-Boost-1.PNG" width=auto />
  <figcaption>Deploy Boost Invocation</figcaption>
</figure>

## Boost Unzip Progress

This steps is very slow, so be patient.

<figure>
  <img src="../images/5-Deploy-Boost-2.PNG" width=auto />
  <figcaption>Unzip Boost Archive</figcaption>
</figure>

## CPU and Memory Usage

CPU Usage during the build process can be quite high. It is  best to leave it run and not try to perform other tasks during compilation.

<figure>
  <img src="../images/5-Deploy-Boost-4.PNG" width=auto />
  <figcaption>Boost CPU Usage</figcaption>
</figure>

With tests performed in a Virtual Machine given 32GB of RAM, the max memory usage appears to be around 13GB to 15GB without any custom settings. A VM allocation of 16GB looks to be a good number for those looking to trim the numbers.

<figure>
  <img src="../images/5-Deploy-Boost-5.PNG" width=auto />
  <figcaption>Boost Memory Usage</figcaption>
</figure>

## Successful Completion

While there are stated failed updates and skipped targets, the build appears to work as expected using the Qt tool chain.

As stated in this image, the artifacts are moved to the `1.74.0` boost directory and ready for use in building `WSJT-X`.

<figure>
  <img src="../images/5-Deploy-Boost-6.PNG" width=auto />
  <figcaption>Successful Build</figcaption>
</figure>

## Boost Validation

To ensure the environment picks up the newly built `Boost` libraries, close then re-open the `JTSDK64-Tools` environment.

!!! caution
    This verification does not prove complete functionality, only that the directory or contents are present and `JTSDK64-Tools` sees the library as `Deployed`.

<figure>
  <img src="../images/5-Deploy-Boost-7.PNG" width=auto />
  <figcaption>Boost Presence Validation</figcaption>
</figure>

This concludes building Deploying Boost. If there were no critical failures, you can proceed to building the `WSJT-X` package.