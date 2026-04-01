---
title: How to build and submit packages for OpenMandriva
description: 
published: true
date: 2026-04-01T08:20:19.116Z
tags: cooker, development, guide, packaging
editor: markdown
dateCreated: 2026-04-01T08:18:24.323Z
---

## Making Packages 

You must have packaging tools installed: 

```bash
sudo dnf install packaging-tools
```

These tools give you templates for spec files and tools for building RPMs. You'll start with the various v* tools: 

**vs:** `vs` stands for *vi specfile*. By default it opens a specfile template in Vim, but it respects the `$EDITOR` and `$VISUAL` environment variables. 

**vl:** `vl` is `vs` for libraries. It loads a different template. 

**vp:** `vp` is `vs` for Python modules. It loads a different template. 

**vpl:** `vpl` is `vs` for Perl modules. It loads a different template. 

**vj:** `vj` is `vs` for Java libraries. It loads a different template. 

**vo:** `vo` is `vs` for GNU Octave. It loads a different template. 

### RPM Spec Files 

RPMs are defined by a *specification* file (spec file for short). This file ends with `.spec`, and it describes how to build a piece of software. Spec files can be simple or complex, depending on what is being built. It's beyond the scope of this documentation to describe how to write a spec file, but it is well documented in these places: 

- <https://rpm-packaging-guide.github.io>
- <https://www.redhat.com/en/blog/create-rpm-package>

To begin writing a spec file, use the appropriate `v*` utility to pull up the template you need. As you learn how to write `.spec` files, it may be helpful to start with an existing `.spec` file from another RPM-based distribution. Be aware, however, that because OpenMandriva is its own distribution and not descended from any others, it's likely you'll have to modify the `.spec` file to get it working. 

When you use the `v*` utility to create your `.spec` file, it's created in `~/abf/[package name]`. Work from this directory. 

### Building Your Package 

When you're ready to test building your package for the first time, save your `.spec` file and exit to your CLI. From the `~/abf/[package name]` directory, run this command: 

```bash
abb build
```

Several subdirectories are created: 

- `BUILD` 
- `RPMS` 
- `SRPMS` 

You'll also see a log. If there are errors, use this log to determine how to fix them. The source code for your package should also have been downloaded. If your build succeeded, your RPM is in the `RPMS` directory, and your source RPM is in the `SRPMS` directory. Test installing your RPM and make sure the software works. 

## Submitting Packages

You can experiment locally with building packages as much as you want. Submitting packages requires [account on OpenMandriva ABF system](https://forum.openmandriva.org/t/4439) and on Github. 

1. If your package exists in OpenMandriva already (i.e., you want to bump the version), fork/clone their repository to your Github account and work with your fork. If the package doesn't exist, create a Git repository for it on Github, then clone it down to your machine. 

2. Make your package work locally. This process results in having a local RPM you can install, and the downloaded source code for your package which you'll use later. 

3. Once you have this, you must have an account on https://abf.openmandriva.org. Register for an account. Since there have been spam issues, you'll never get the email to verify your account. You'll have to go onto the Matrix chat and into the Cooker channel to request verification of your account. 

4. Upload the source to https://file-store.openmandriva.org. You got access to this when your ABF account was verified. When it uploads, it displays a hash for the file. 

5. Copy the hash. Create a file in the same folder as your .spec file called `.abf.yml`. 

6. Inside this file, add the file name for the source code you uploaded and its hash in this format: 

   ```
   sources:
     [source code file name]: [hash number]
   ```

7. Commit the `.spec` and the `.abf.yml` files (but not anything else) to the repository. Push it to your Github account. 

8. Log into <https://abf.openmandriva.org>. 

9. Select *Projects* from the menu on the left, and then select *New Project*. 

10. Under Project Name, type the name of your Github repository, which should match the name of the software in all lower case. Select the Owner as *Myself*. 

11. Under Github organization, type your Github user name. 

12. Check *Project is a package*. 

13. Under Maintainer of Project, your ABF user name should already be populated. 

14. Click *Save*. Now the project appears in your list of projects on ABF. 

15. In that list, click *New Build*. 

16. Under Build for Platform, select *main* under Cooker. 

17. Under Architecture, select *x86_64*. 

18. If your personal repository appears under Extra Repositories, click the red X to remove it. 

19. Use cached chroot and Use extra tests are checked by default; leave them. 

20. Click *Start Build*.

21. If the build succeeds start another build, and this time select the other architectures: *aarch64* and *znver1*.

22. If that build succeeds, send a pull request. 

23. If the build was for a new package, notify the OpenMandriva devs in the Cooker channel on Matrix. A member of the dev team then creates an OpenMandriva repository. 

24. Fork/clone OM's repository, re-commit your `.spec` and `.abf.yml` files to the new repository, and send them a pull request. 

## Installing Your Submitted Package 

When your package gets merged, it doesn't appear in OpenMandriva Rome or Rock right away. It goes into the development branch, Cooker. It is not recommended to run Cooker as a daily driver; it breaks. Instead, you can install your package by specifying the Cooker repo where it was built. 

**Note:** Do *not* add Cooker repositories to your system. You will break your ROME or Rock system. 
Set up a cooker virtual machine or install cooker to a dedicated separate partition.

If your package is an upgrade, use this command: 

```bash
sudo dnf upgrade --enablerepo=[repo name] [package name]
```

If your package is a new installation, use this command: 

```bash
sudo dnf install --enablerepo=[repo name] [package name] 
```

For example, if you submitted a version bump for, say, Syncthing, and it got merged, use this command to install the upgraded version on your system running Rome or Rock: 

```bash
sudo dnf upgrade --enablerepo=cooker-x86_64 syncthing
```

Similarly, if you submitted a new package, say Vifm, and it got merged, use this command to install it on your system running Rome or Rock: 

```bash
sudo dnf install --enablerepo=cooker-x86_64-extra vifm
```

----
*Credits: sez11a
https://forum.openmandriva.org/t/7550*
