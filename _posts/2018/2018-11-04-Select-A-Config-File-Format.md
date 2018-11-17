---
layout: post
title: Select a configuration file format
category: python
tags: [python]
---

# Select a configuration file format which 

## Background
*******

On the way searching on the internet how to select a good method to write config file.
I found a very good article on [#PEP-0518] comparing between file formats.
I copied the part that I think very interest.

## Other file formats
*******

Several other file formats were put forward for consideration, all
rejected for various reasons. Key requirements were that the format
be editable by human beings and have an implementation that can be
vendored easily by projects. This outright excluded certain formats
like XML which are not friendly towards human beings and were never
seriously discussed.

## Overview of file formats considered
*******

The key reasons for rejecting the other alternatives considered are
summarised in the following sections, while the full review (including
positive arguments in favour of TOML) can be found at [#file_formats]_.

TOML was ultimately selected as it provided all the features we
were interested in, while avoiding the downsides introduced by
the alternatives.

Feature                 | TOML | YAML | JSON | CFG/INI | XML
------------------------|------|------|------|---------|----
Well-defined            | yes  | yes  | yes  |         | yes
Real data types         | yes  | yes  | yes  |         | yes
Reliable Unicode        | yes  | yes  | yes  |         | yes
Reliable comments       | yes  | yes  |      |         | ??
Easy for humans to edit | yes  | ??   |      | ??      |
Easy for tools to edit  | yes  | ??   | yes  | ??      | yes
In standard library     |      |      | yes  | yes     | yes
Easy for pip to vendor  | yes  |      | n/a  | n/a     | n/a


("??" in the table indicates items where most folks would be
inclined to answer "yes", but there turn out to be a lot of
quirks and edge cases that arise in practice due to either
the lack of a clear specification, or else the underlying
file format specification being surprisingly complicated)

The ``pytoml`` TOML parser is ~300 lines of pure Python code,
so being outside the standard library didn't count heavily
against it.

Python literals were also discussed as a potential format, but
weren't considered in the file format review (since they're not
a common pre-existing file format).


### JSON
*******

The JSON format [#json]_ was initially considered but quickly
rejected. While great as a human-readable, string-based data exchange
format, the syntax does not lend itself to easy editing by a human
being (e.g. the syntax is more verbose than necessary while not
allowing for comments).

An example JSON file for the proposed data would be::

    {
        "build": {
            "requires": [
                "setuptools",
                "wheel>=0.27"
            ]
        }
    }


### YAML
*******

The YAML format [#yaml]_ was designed to be a superset of JSON
[#json]_ while being easier to work with by hand. There are three main
issues with YAML.

One is that the specification is large: 86 pages if printed on
letter-sized paper. That leaves the possibility that someone may use a
feature of YAML that works with one parser but not another. It has
been suggested to standardize on a subset, but that basically means
creating a new standard specific to this file which is not tractable
long-term.

Two is that YAML itself is not safe by default. The specification
allows for the arbitrary execution of code which is best avoided when
dealing with configuration data.  It is of course possible to avoid
this behavior -- for example, PyYAML provides a ``safe_load`` operation
-- but if any tool carelessly uses ``load`` instead then they open
themselves up to arbitrary code execution. While this PEP is focused on
the building of projects which inherently involves code execution,
other configuration data such as project name and version number may
end up in the same file someday where arbitrary code execution is not
desired.

And finally, the most popular Python implemenation of YAML is
PyYAML [#pyyaml]_ which is a large project of a few thousand lines of
code and an optional C extension module. While in and of itself this
isn't necessarily an issue, this becomes more of a problem for
projects like pip where they would most likely need to vendor PyYAML
as a dependency so as to be fully self-contained (otherwise you end
up with your install tool needing an install tool to work). A
proof-of-concept re-working of PyYAML has been done to see how easy
it would be to potentially vendor a simpler version of the library
which shows it is a possibility.

An example YAML file is::

    build:
        requires:
            - setuptools
            - wheel>=0.27


### configparser
*******

An INI-style configuration file based on what
configparser [#configparser]_ accepts was considered. Unfortunately
there is no specification of what configparser accepts, leading to
support skew between versions. For instance, what ConfigParser in
Python 2.7 accepts is not the same as what configparser in Python 3
accepts. While one could standardize on what Python 3 accepts and
simply vendor the backport of the configparser module, that does mean
this PEP would have to codify that the backport of configparser must
be used by all project wishes to consume the metadata specified by
this PEP. This is overly restrictive and could lead to confusion if
someone is not aware of that a specific version of configparser is
expected.

An example INI file is::

    [build]
    requires =
        setuptools
        wheel>=0.27


### Python literals
*******

Someone proposed using Python literals as the configuration format.
The file would contain one dict at the top level, with the data all
inside that dict, with sections defined by the keys. All Python
programmers would be used to the format, there would implicitly be no
third-party dependency to read the configuration data, and it can be
safe if parsed by ``ast.literal_eval()`` [#ast_literal_eval]_.
Python literals can be identical to JSON, with the added benefit of
supporting trailing commas and comments. In addition, Python's richer
data model may be useful for some future configuration needs (e.g. non-string
dict keys, floating point vs. integer values).

On the other hand, python literals are a Python-specific format, and
it is anticipated that these data may need to be read by packaging
tools, etc. that are not written in Python.

An example Python literal file for the proposed data would be::

    # The build configuration
    {"build": {"requires": ["setuptools",
                            "wheel>=0.27", # note the trailing comma
                            # "numpy>=1.10" # a commented out data line
                            ]
    # and here is an arbitrary comment.
               }
     }


###  Sticking with ``setup.cfg``
*******

There are two issues with ``setup.cfg`` used by setuptools as a general
format. One is that they are ``.ini`` files which have issues as mentioned
in the configparser_ discussion above. The other is that the schema for
that file has never been rigorously defined and thus it's unknown which
format would be safe to use going forward without potentially confusing
setuptools installations.

## References
==========
1. [#PEP-0518]
2. [#distutils]
3. [#setuptools]
4. [#setup_args]
5. [#pip]
6. [#wheel]
7. [#toml]
8. [#json]
9.  [#yaml]
10. [#configparser]
11. [#pyyaml]
12. [#pypa]
13. [#bazel]
14. [#ast_literal_eval]
15. [#cargo]
16. [#jsonschema]
17. [#file_formats]
   
[#PEP-0518]:https://www.python.org/dev/peps/pep-0518/#toml
[#distutils]:https://docs.python.org/3/library/distutils.html#module-distutils
[#setuptools]:https://pypi.python.org/pypi/setuptools
[#setup_args]:http://pythonhosted.org/setuptools/setuptools.html#new-and-changed-setup-keywords
[#pip]:https://pypi.python.org/pypi/pip
[#wheel]:https://pypi.python.org/pypi/wheel
[#toml]:https://github.com/toml-lang/toml
[#json]:http://json.org/
[#yaml]:http://yaml.org/
[#configparser]:https://docs.python.org/3/library/configparser.html#module-configparser
[#pyyaml]:https://pypi.python.org/pypi/PyYAML
[#pypa]:https://www.pypa.io
[#bazel]:http://bazel.io/
[#ast_literal_eval]:https://docs.python.org/3/library/ast.html#ast.literal_eval
[#cargo]:http://doc.crates.io/
[#jsonschema]:http://json-schema.org/
[#file_formats]:https://gist.github.com/njsmith/78f68204c5d969f8c8bc645ef77d4a8f


Copyright
=========

Content of this document has been placed in the [public domain](https://github.com/python/peps/blob/master/pep-0518.txt).