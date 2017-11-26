# MSVC Win32 MDI Application

## Table of Contents

- [Introduction](#introduction)
- [Windows Target Version](#windows-target-version)
- [Distributing Your Application](#distributing-your-application)
- [Terms of Use](#terms-of-use)
- [Problems?](#problems)
- [Changelog](#changelog)

## Introduction

This application is an example Windows MDI GUI application. The compiled application is fully functional, with the
exception that opening and saving files does not read or write the files, and the MDI child windows do not have any code
to display documents. However, by adding this functionality you can quickly create a functioning MDI application.

To build the application, open the solution file in Visual Studio, right click the solution in the Solution Explorer and
select "Retarget solution". Choose which version of the Windows SDK you'd like to use to build the solution. Next,
select the configuration and platform from the drop-down menu, and use "Build Solution" from the "Build" menu.

The solution was created in Visual Studio 2017, but it should open in any version of Visual Studio from 2010 SP1
onwards.

## Windows Target Version

The project targets Windows Vista. If you attempt to call Windows API functions in your source code which were
introduced after Windows Vista, you will get a compilation error. If you'd like to use newer API functions (at the
expense of the application not running on older versions of Windows), you will need to change the "_WIN32_WINNT"
preprocessor definition in "targetver.h" to match the version of Windows you are targeting. For example, to target
Windows 7, change it to "0x0601".

You can also target Windows XP using the above method with the value "0x0501". However, you will also need to go into
your project properties, and set the "Platform Toolset" under "Configuration Properties" to a toolset which supports
Windows XP.

You can find a complete list of target version numbers in the "SDKDDKVer.h" Windows SDK header file.

## Distributing Your Application

The application will depend on the Microsoft Visual C++ Runtime. This will either be in the form of a Visual C++ Runtime
redistributable MSI (or merge module which you can use in your own installer), or DLL(s) which you must redistribute
with the application. Check the product documentation for your version of Visual Studio to see what your options are,
and be careful to ensure that you are allowed to redistribute the DLL(s) if you choose this option.

## Terms of Use

Refer to "License.txt" for terms of use.

## Problems?

If you have any problems or questions, please ensure you have read this readme. If you are still having trouble, you can
[get in contact](http://www.transmissionzero.co.uk/contact/).

## Changelog

1. 2017-08-15: Version 1.0
  - Initial release.

Transmission Zero
2017-08-15
