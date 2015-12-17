# Pex Rules

<div class="toc">
  <h2>Rules</h2>
  <ul>
    <li><a href="#pex_library">pex_library</a></li>
    <li><a href="#pex_binary">pex_binary</a></li>
  </ul>
</div>

## Overview

These build rules are used for building [Pex][pex] projects with Bazel.

[pex]: https://github.com/pantsbuild/pex

<a name="pex_library"></a>
## pex_library

```python
pex_library(name, srcs, deps, eggs)
```

<table class="table table-condensed table-bordered table-params">
  <colgroup>
    <col class="col-param" />
    <col class="param-description" />
  </colgroup>
  <thead>
    <tr>
      <th colspan="2">Attributes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>name</code></td>
      <td>
        <code>Name, required</code>
        <p>A unique name for this rule.</p>
      </td>
    </tr>
    <tr>
      <td><code>srcs</code></td>
      <td>
        <code>List of labels, required</code>
        <p>List of Python <code>.py</code> source files used to build the
        library.</p>
      </td>
    </tr>
    <tr>
      <td><code>deps</code></td>
      <td>
        <code>List of labels, optional</code>
        <p>List of other libraries to be linked to this library target.</p>
      </td>
    </tr>
    <tr>
      <td><code>eggs</code></td>
      <td>
        <code>List of labels, optional</code>
        <p>List of Python eggs <code>.egg</code> files or wheel
        <code>.whl</code> files used by this rule at runtime.</p>
      </td>
    </tr>
  </tbody>
</table>

<a name="pex_binary"></a>
## pex_binary

```python
pex_binary(name, srcs, deps, eggs, resources, main, zip_safe)
```

<table class="table table-condensed table-bordered table-params">
  <colgroup>
    <col class="col-param" />
    <col class="param-description" />
  </colgroup>
  <thead>
    <tr>
      <th colspan="2">Attributes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>name</code></td>
      <td>
        <code>Name, required</code>
        <p>A unique name for this rule.</p>
      </td>
    </tr>
    <tr>
      <td><code>main</code></td>
      <td>
        <code>Label, required</code>
        <p>
          The main entry point for the pex. This Python <code>.py</code> file
          will be executed when the pex binary is invoked.
        </p>
      </td>
    </tr>
    <tr>
      <td><code>srcs</code></td>
      <td>
        <code>List of labels, required</code>
        <p>List of Python <code>.py</code> source files used to build the
        binary.</p>
      </td>
    </tr>
    <tr>
      <td><code>deps</code></td>
      <td>
        <code>List of labels, optional</code>
        <p>List of other libraries to be linked to this binary target.</p>
      </td>
    </tr>
    <tr>
      <td><code>eggs</code></td>
      <td>
        <code>List of labels, optional</code>
        <p>List of Python eggs <code>.egg</code> files or wheel
        <code>.whl</code> files used by this rule at runtime.</p>
      </td>
    </tr>
    <tr>
      <td><code>resources</code></td>
      <td>
        <code>List of labels, optional</code>
        <p>
          Any file type to be included in final pex that can be accessed by
          python code. <code>filedeps</code> targets can also be included.
        </p>
      </td>
    </tr>
    <tr>
      <td><code>zip_safe</code></td>
      <td>
        <code>Boolean, optional, default is true</code>
        <p>
          Whether or not this binary is safe to run in compacted (zip-file)
          form. If set to <code>false</code>, the pex will be automatically
          unzipped before executing.
        </p>
        <p>
          This is mostly useful when a lot of resource files are bundled with
          the pex, and require direct file access. An example is large html, css
          and javascript files for a web server.
        </p>
      </td>
    </tr>
  </tbody>
</table>
