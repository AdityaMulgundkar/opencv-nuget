# OpenCV NuGet Package with support for multiple msvc versions

## Status Report - OpenCVNuget
OpenCVNuget package is built for simpler importing of the [OpenCV project](https://github.com/opencv/opencv) in C++ projects. NuGet provides ease of installation with the ability to produce and consume packages quickly. Using a NuGet package avoids the requirement of manually building the OpenCV project using CMake and importing (linking and configuring) the relevant lib and dll files in your project.

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


### NuGet packages (releases)