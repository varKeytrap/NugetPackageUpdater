﻿## Simple nuget package updater for Squirrel-based projects

Usage :

1. Place the NugetPackageUpdater.exe in the root of your project (where are your .npkg e.g: MyPackage.1.0.1.npg)
2. Call the exe `NugetPackageUpdater.exe --current MyPackage.1.0.1.npg --new MyPackage.1.0.2.npg --ignored-extensions "xml,pdb"`

The `-i or --ignored-extensions` argument is optional

Behind the scenes :

It will first extract MyPackage.1.0.1.npg in {root}\Releases\MyPackage.1.0.1.npg
It will find the lib directory and clear it
It fetches all files from {root}\bin\Releases (except file having an ignored extension) and copies them back to {root}\Releases\MyPackage.1.0.1.npg
It updates the .nuspec file with the new version of the package
Zips the {root}\Releases\MyPackage.1.0.1.npg to {root}\MyPackage.1.0.2.npkg

And you're ready to releasify with Squirrel

Disclaimer : this is not suitable for real production it may contain bugs but it was just something I needed as I found the manual processes painful.