---
layout: default-layout
title: User Guide for C Language
keywords: user guide, hello world
description: Dynamsoft Document Normalizer - User Guide for C Language
---

# User Guide for C Language

In this guide, you will learn step by step on how to build a document normalization application with Dynamsoft Document Normalizer SDK using C language.

## Requirements

- Operating System:
  - Windows 7, 8, 10, 11
  - Windows Server 2003, 2008, 2008 R2, 2012, 2016, 2019, 2022
  - Linux x64: Ubuntu 14.04.4+ LTS, Debian 8+, etc

- Developing Tool
  - Visual Studio 2008 or above
  - GCC 5.4+  

## Installation

If you haven't downloaded the SDK yet, <a href="https://download2.dynamsoft.com/ddn/dynamsoft-document-normalizer-c_cpp-1.0.20.zip">download the `C/C++ Package`</a> now and unpack the package into the directory of your choice.

>For this tutorial, we unpack it to `[INSTALLATION FOLDER]`, change it to your unpacking path for the following content.

## Build Your First Application

Let's start by creating a console application which demonstrates how to use the minimum code to detect and normalize document from an image file.  
>You can <a href="https://github.com/Dynamsoft/document-normalizer-c-cpp-samples/tree/main/Samples/C/HelloWorld" target="_blank">download the entire source code from here</a>.

### Create a New Project

- For Windows

1. Open Visual Studio. Go to File > New > Project, create a new Empty Project and set Project name as `DDNCSample`.

2. Add a new source file named `DDNCSample.c` into the project.

- For Linux

1. Create a new source file named `DDNCSample.c` and place it into the folder `[INSTALLATION FOLDER]/Samples`.

### Include the Library

1. Add headers and libs in `DDNCSample.c`.

    ```c
    #include <stdio.h>
    #include "[INSTALLATION FOLDER]/Include/DynamsoftDocumentNormalizer.h"
    #if defined(_WIN64) || defined(_WIN32)
        #ifdef _WIN64
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftCorex64.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x64/DynamsoftDocumentNormalizerx64.lib")
        #else
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftCorex86.lib")
            #pragma comment(lib, "[INSTALLATION FOLDER]/Lib/Windows/x86/DynamsoftDocumentNormalizerx86.lib")
        #endif
    #endif
    ```

### Initialize a Document Normalizer Instance

1. Initialize the license key.

    ```c
    char szErrorMsg[256];
    DC_InitLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", szErrorMsg, 256);
    ```

    > The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here is a free public trial license. Note that network connection is required for this license to work. When it expires, you can
    > request a 30-day free trial license from <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=ddn&package=desktop" target="_blank">Customer Portal</a>.

2. Create an instance of Dynamsoft Document Normalizer.

    ```c
    void *ddn = DDN_CreateInstance();
    ```

### Detect and Save the Normalized Document

1. Apply normalization for an image file.

    ```c
    int errorCode = 0;
    NormalizedImageResult* normalizedResult = NULL;
    errorCode = DDN_NormalizeFile(ddn, "[INSTALLATION FOLDER]/Images/sample-image.png", "", NULL, &normalizedResult);
    if(errorCode != DM_OK)
        printf("%s\n", DC_GetErrorString(errorCode));
    ```

    >For the error handling mechanism, the SDK returns Error Code for each function and provides a function `DC_GetErrorString` to get the readable message. You should add codes for error handling based on your needs. Check out [Error Code]({{site.enumerations}}error-code.html) for full supported error codes.

2. Save the normalized result as an image file.

    ```c
    if (normalizedResult != NULL)
    {
        DDN_SaveImageDataToFile(normalizedResult->image, "result-image.png");
    }
    ```

### Release Allocated Memory

1. Release the allocated memory for the normalized result and instance.

    ```c
    if (normalizedResult != NULL)
        DDN_FreeNormalizedImageResult(&normalizedResult);
    DDN_DestroyInstance(ddn);
    ```

>Note:  
Please change all `[INSTALLATION FOLDER]` in above code snippet to your unpacking path.

### Build and Run the Project

- For Windows

1. In Visual Studio, set the solution to build as Release\|x64.

2. Build the project to generate program `DDNCSample.exe`.

3. Copy **ALL** `*.dll` files under `[INSTALLATION FOLDER]\Lib\Windows\x64` to the same folder as the `DDNCSample.exe`.

4. Run the program `DDNCSample.exe`.

>The SDK supports both x86 and x64, please set the platform based on your needs.

- For Linux

1. Open a terminal and change to the target directory where `DDNCSample.c` located in. Build the sample:

    ```bash
    gcc -o DDNCSample DDNCSample.c -lDynamsoftCore -lDynamsoftDocumentNormalizer -L ../Lib/Linux -Wl,-rpath=../Lib/Linux
    ```

2. Run the program `DDNCSample`.

    ```bash
    ./DDNCSample
    ```

>You can <a href="https://github.com/Dynamsoft/document-normalizer-c-cpp-samples/tree/main/Samples/C/HelloWorld" target="_blank">download the entire source code from here</a>.
