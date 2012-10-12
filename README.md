# Ruby Puppet Module for Boxen

Requires the following boxen modules:

* `boxen`
* `rbenv`

## Usage

```puppet
# ensure a certain ruby version is used in a dir
ruby::local { '/path/to/some/project':
  version => '1.9.3-p194'
}

# ensure a gem is installed for a certain ruby version
# note, you can't have duplicate resource names so you have to name like so
ruby::gem { "bundler for ${version}":
  gem     => 'bundler',
  ruby    => $version,
  version => '~> 1.2.0'
}

# install a ruby version
ruby { '1.9.3-p194':
  global => true
}

# we provide a ton of predefined ones for you though
require ruby::1-9-3-p194
```