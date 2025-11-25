# g.extension

**Category**: general

## Description

Maintains GRASS Addons extensions in local GRASS installation. Downloads and installs extensions from GRASS Addons repository or other source into the local GRASS installation or removes installed extensions.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_extension(extension,operation="add",url=None,prefix="$GRASS_ADDON_BASE",proxy=None,branch=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`extension : str, required`**
   - Name of extension to install or remove
   - Name of toolbox (set of extensions) when -t flag is given
   - Used as: name

2. **`operation : str, required`**
   - Operation to be performed
   - Allowed values: add, remove
   - Default: add

3. **`url : str, optional`**
   - URL or directory to get the extension from (supported only on Linux and Mac)
   - The official repository is used by default. User can specify a ZIP file, directory or a repository on common hosting services. If not identified, Subversion repository is assumed. See manual for all options.
   - Used as: url

4. **`prefix : str, optional`**
   - Prefix where to install extension (ignored when flag -s is given)
   - Used as: path
   - Default: $GRASS_ADDON_BASE

5. **`proxy : str | list[str], optional`**
   - Set the proxy with: "http=<value>,ftp=<value>"
   - Used as: proxy

6. **`branch : str, optional`**
   - Specific branch to fetch addon from (only used when fetching from git)
   - Used as: branch

7. **`flags : str, optional`**
   - Allowed values: l, c, g, a, s, d, i, f, t, o
   - l
   - List available extensions in the official GRASS Addons repository
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.extension.html#__tabbed_2_3) for all details)*

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

g.extension downloads and installs, removes or updates extensions
(addons) from the official GRASS Addons
repository or from
user-specified source code repositories into the local GRASS
installation.

Two types of extensions are supported:

Re-running g.extension on an installed GRASS Addon extension
re-installs the requested extension which may include updates.

To bulk-update all locally installed GRASS extensions, g.extension.all module is available.

GRASS extensions are installed by g.extension into a dedicated
directory. The default is a directory for application data and settings
inside the user's home directory. On GNU/Linux it is $HOME/.grass8/addons , on MS-Windows it is %APPDATA%\Roaming\GRASS8\addons . The name of the directory is stored
in the GRASS_ADDON_BASE environmental variable.

The flag -s changes this install target directory to the GRASS
installation directory (determined by GISBASE environmental variable,
e.g. /usr/ ) rather than the default directory defined as per GRASS_ADDON_BASE (see also documentation for variables ). g.extension checks if the user has
permission to write to GISBASE or GRASS_ADDON_BASE .

The place where the extensions are installed can be customized by the
option prefix . Ensuring that these extensions will be accessible in
GRASS is in this case in the responsibility of the user.

By default, g.extension installs extensions from the official GRASS
Addons GitHub repository. However, different sources can be
specified using the url option.

Individual extensions can also be installed by providing a URL to the
source code on GitHub or OSGeo Trac. The latter, however, works only for
certain directories where the download of ZIP files was enabled by
project administrators of the trac server.

Optionally, new extension can be also installed from a source code
placed in a local directory on disk. This is advantageous when
developing a new module. To keep the directory clean, the directory
content is copied to a temporary directory and the compilation happens
there.

In addition, new extension can be also installed from a ZIP file or an
archive file from the TAR family (e.g., .tar.gz or .bz2 ). The file
can be on disk (specified with a path), or on the web (specified by an
URL).

For well known general hosting services, namely GitHub, GitLab and
Bitbucket, g.extension supports the download of a repository. Here the
user only needs to provide a base URL to the repository web page (with
or without the https:// part). For GitHub, GitLab and Bitbucket, the
latest source code in the default branch is downloaded, unless a
specific branch is requested in the branch option. Of course, a user
can still specify the full URL of a ZIP file e.g. for a specific release
and install the archived code in this way (ZIP file mechanism will be
applied).

For the official repository, g.extension supports listing available
extensions (addons) and few other metadata-related operations which
depend on a specific infrastructure. For other sources and repositories,
this is not supported because it is assumed that other sources contain
only one extension, typically a module or group of modules with a
Makefile at the root of the repository.

When none of the above sources is identified, g.extension assumes that
the source is in a GitHub repository and uses the git command line
tool to obtain the source code. The expected structure of the repository
should be the same as the one of the official repository.

Non-official sources are supported on all operating systems except for
MS-Windows.

On MS-Windows systems, where compilation tools are typically not readily
locally installed, g.extension downloads a precompiled executable from
the GRASS project server. On all other operating systems where it is
not difficult to install compilation tools, g.extension downloads the
source code of the requested extension (addon) and compiles it locally.
This applies for both C and Python modules as well as any other
extensions. The reason is that more things such as manual page are
compiled, not only the source code (which is really necessary to compile
just in case of C).

---

## See Also

Related tools:
- [`g.extension.all`](https://grass.osgeo.org/grass-devel/manuals/g.extension.all.html)

---

## Authors

Markus Neteler (original shell script) Martin Landa, Czech Technical University in Prague, Czech Republic
(Python rewrite) Vaclav Petras, NCSU GeoForAll
Lab (support for general
sources, partial refactoring)

---

## Resources

- [Official g.extension manual](https://grass.osgeo.org/grass-devel/manuals/g.extension.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.extension.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
