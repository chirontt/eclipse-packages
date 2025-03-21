# Eclipse Packaging Project Change Log

The Eclipse Packaging Project (EPP) assembles the contents of the quarterly Eclipse Simultaneous Release (SimRel) into products that can be downloaded from the [Eclipse IDE website](https://eclipseide.org).
This document aims to highlight configuration and content changes of the packages provided by EPP in each quarterly release.
For changes in Eclipse projects that contribute to SimRel and are included in the EPP packages, refer to the change log or New and Noteworthy document of the participating projects.
The [Eclipse IDE New & Noteworthy](https://eclipseide.org/release/noteworthy/) page combines all those documents in one place.

## 2025-03

- The default `eclipse.ini` generally no longer includes `-Xmx` and `-Xms` arguments for the JVM. This means that the JVM will use its internal algorithm for determining `-Xmx` and `-Xms` values. Some users may want to add `-Xmx` and `-Xms` arguments to their `eclipse.ini` if they have particularly small or large memory.

## 2024-12

- [TextMate 4 Eclipse (TM4E)](https://projects.eclipse.org/projects/technology.tm4e) is now included with all packages. The TM4E project uses the Generic Code Editor in Eclipse to support syntax highlighting for a large number of languages.
- The Eclipse Packaging Project contains 2 new OS / CPU Architecture pairs. Windows on ARM and Linux on RISC-V are now built for all packages for each release.
- The Windows operating system trust store is now used by default instead of the cacerts bundled with the JVM. This is controlled by the new command line options `-Djavax.net.ssl.trustStoreType=Windows-ROOT` and `-Djavax.net.ssl.trustStore=NONE` in the eclipse.ini file.

## 2024-06

- Eclipse IDE now ships with Java 21 by default and many of the individual downloads now require Java 21.
- The Eclipse IDE for C/C++ Developers now includes the [CDT-LSP](https://github.com/eclipse-cdt/cdt-lsp) set of features to provide a Language Server for C/C++ users.

## 2023-12

- The Eclipse IDE for Scientific Computing is not longer being published. If you are interested in helping maintain or resurrect this package, and the underlying Parallel Tools Project, please [leave a comment](https://github.com/eclipse-packaging/packages/issues/85). 
- Eclipse [contains a new backend](https://eclipse.dev/eclipse/news/4.30/platform.php#new-ecf-client) used by P2 to install and update software. The Eclipse Packaging Project [has disabled this by default](https://github.com/eclipse-packaging/packages/issues/81) as it is [known to not work in some corporate environments](https://github.com/eclipse-equinox/p2/issues/381). Please help test the new backend by removing `-Dorg.eclipse.ecf.provider.filetransfer.excludeContributors=org.eclipse.ecf.provider.filetransfer.httpclientjava` from eclipse.ini and [reporting any issues you have](https://github.com/eclipse-equinox/p2/issues/new/choose) so that the new backend can be the default in the near future.
- The PDE Spies has been restored to the Eclipse IDE for RCP and RAP Developers.

## 2023-09

- Packages now contain configuration and start levels for logging support.
This change applies the [recommendation](https://eclipse.dev/eclipse/news/4.28/platform.php#slf4j.api-version-2) from Eclipse Platform to support SLF4J version 2.
For implementation details refer to [EPP Issue #27](https://github.com/eclipse-packaging/packages/issues/27).
- With the new Mylyn major version being released the list of features included in packages have been updated to their new names and IDs.
- The Eclipse IDE for RCP and RAP Developers is missing the PDE Spies, this can be manually installed by selecting "Eclipse Plug-in Development Environment Spies" in the Install New Software wizard.

## 2023-06

- With [Eclipse Mylyn](https://eclipse.dev/mylyn/)'s return to the SimRel train Mylyn features have also been added back to all the EPPs, except Eclipse IDE for Java and DSL Developers.

## Prior to 2023-06

This Changelog was introduced for release 2023-09 and backfilled to 2023-06.
If you require additional information about older versions to be added to this changelog, please [raise an issue](https://github.com/eclipse-packaging/packages/issues).
