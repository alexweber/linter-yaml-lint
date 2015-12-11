linter-yaml-lint
=========================
[![Build Status](https://travis-ci.org/alexweber/linter-yaml-lint.svg?branch=master)](https://travis-ci.org/alexweber/linter-yaml-lint)
[![Dependency Status](https://david-dm.org/alexweber/linter-yaml-lint.svg)](https://david-dm.org/alexweber/linter-yaml-lint)
[![Plugin installs!](https://img.shields.io/apm/dm/linter-yaml-lint.svg)](https://atom.io/packages/linter-yaml-lint)
[![Package version!](https://img.shields.io/apm/v/linter-yaml-lint.svg?style=flat)](https://atom.io/packages/linter-yaml-lint)

This linter plugin for [Linter](https://github.com/AtomLinter/Linter) provides an interface to [yaml-lint](https://github.com/Pryz/yaml-lint). It will be used with files that have the “YAML syntax.

### Installation
Linter package will automatically be installed for you if you do not already have it.

#### yaml-lint installation
Before using this plugin, you must ensure that `yaml-lint` is installed on your system. To install `yaml-lint`, do the following:

1. Install [ruby](https://www.ruby-lang.org/).

2. Install [yaml-lint](https://github.com/Pryz/yaml-lint) by typing the following in a terminal:
   ```
   gem install yaml-lint
   ```

Now you can proceed to install the linter-yaml-lint plugin.

#### Plugin installation
```
$ apm install linter-yaml-lint
```

### Settings
You can configure linter-yaml-lint by editing ~/.atom/config.cson (choose Open Your Config in Atom menu):
```cson
'linter-yaml-lint':

  # Optionally specify additional arguments to be passed to `yaml-lint`.
  # Run `yaml-lint -h` to see available options.
  'additionalArguments': null

  # Optionally disable `yaml-lint` if you don't have an ``.yaml-lint.yml` in
  # your project directory
  'disableWhenNoConfigFileInPath': false

  # The `yaml-lint` path. Run `which yaml-lint` to find this path.
  'executablePath': null
```

### Config file
Linter will start looking for `.yaml-lint.yml` file in the same directory as the file that's being linted. If not found, it will move one level up the directory tree all the way up to the filesystem root (If you enabled `disableWhenNoConfigFileInPath`, then it will not search further).


### Using `rvm`

If you are using `rvm`, you will need a wrapper for `yaml-lint` to run properly.  There are a couple options for this (see below).

**_NOTE:_** *If you are seeing* `Error: env: ruby_executable_hooks: No such file or directory` *then you need to do this!*

Consult rvm docs for further info not covered in this README - https://rvm.io/

##### Wrapper just for atom

This will create a wrapper just for atom using your current ruby version:

```bash
$ rvm wrapper current atom yaml-lint
```

Then in `linter-yaml-lint` set `executablePath` to `/path/to/rvm/bin/atom_yaml-lint`

*Note: you can find rvm path using* `which rvm`

##### Wrapper for ruby version

You can also just use the wrapper generated for a particular ruby version.  This may already be generated.  To check:

```bash
$ ls -al /path/to/rvm/gems/ruby-x.y.z/wrappers
```

If `yaml-lint` isn't in there, generate the wrappers:

```bash
$ rvm wrapper current
```

Then in `linter-yaml-lint` set `executablePath` to `/path/to/rvm/gems/ruby-x.y.z/wrappers/yaml-lint`


### Contributing
If you would like to contribute enhancements or fixes, please do the following:

1. Fork the plugin repository.
1. Hack on a separate topic branch created from the latest `master`.
1. Commit and push the topic branch.
1. Make a pull request.
1. welcome to the club

Please note that modifications should follow these coding guidelines:

- Indent is 2 spaces.
- Code should pass coffeelint linter.
- Vertical whitespace helps readability, don’t be afraid to use it.

Thank you for helping out!
