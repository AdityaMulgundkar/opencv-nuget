# OpenCV NuGet Package with support for multiple msvc versions

## Status Report - OpenCVNuget
OpenCVNuget package is built for simpler importing of the [OpenCV project](https://github.com/opencv/opencv) in C++ projects. NuGet provides ease of installation with the ability to produce, distribute and consume packages quickly. Using a NuGet package avoids the requirement of manually building the OpenCV project using CMake and importing (linking and configuring) the relevant lib and dll files in your project.

## Mentors
- Miguel Lourenço

## Important Links
- [GSoC Project](https://summerofcode.withgoogle.com/projects/#6336151138336768)
- [OpenCV GitHub Repository](https://github.com/opencv/opencv)
- [Final Pull Request](https://github.com/opencv/opencv/pull/20389)

## Goals
- To create a workflow that can be used to generate the NuGet package whenever the base opencv project version is updated
- To automate the NuGet package generation
- To generate the NuGet package with multiple msvc versions

## Final Status
A Github Actions workflow has been created in order to imitate the entire process of building the .nupkg file:
- CMake for building OpenCV from source
- Templatized generation of .nuspec and .targets files
- Importing build files into .nuspec, .targets and final output directory
- Building (or packing) the final .nupkg file
- Providing the .nupkg as a downloadable artifact

### Code structure
- This repository is housed inside the [OpenCV repository](https://github.com/opencv/opencv) under the `platforms/nuget` directory
- `build-jinja.py` file parses and generates the .nuspec and .targets files
- The templates folder contains jinja templates of .nuspec and .targets files
- The workflow folder contains a Github Actions workflow, which can easily be integrated by forking the OpenCV repository (as documented in [CLONING.md](CLONING.md))

### NuGet packages (releases)
The [releases section](https://github.com/AdityaMulgundkar/opencv-nuget/releases) contains the following pre-built NuGet packages for distribution:
- Visual Studio 2019 - msvc 16.0
- Visual Studio 2018 - msvc 15.0
- Visual Studio 2017 - msvc 14.0

(all above packages support x64 in debug + release mode)

## Guides & Tutorials
- [Cloning](CLONING.md) - Guide to Forking & Creating the Github Action on your own clone of opencv repository
- [Tutorial](TUTORIAL.md) - Tutorial for using the NuGet package (.nupkg file) in your projects

## Future Work
- Extending the workflow to build opencv-contrib
- Allowing configuration of individual opencv modules in the workflow