# smartless

`smartless` is a pager that behaves just like `less`, but will show the file (or output) directly to the terminal if it is short enough (15 lines by default).  For longer files, the 

## Prerequisites

`smartless` requires a reasonable resent version of `bash`, and a pager like `less`.  Both are available by default on most unix systems.

## Usage

`smartless` is designed as a drop-in replacement for `less`.  For instance, to view the output of a command `cmd`, use

    cmd | smartless

It is also possible to pass a filename directly:

    smartless file.txt

Finally, all other parameters are forwarded to the pager.  For instance, `smartless +G` will jump to the end of the file in `less`.

### Aliases

To replace less completely, it is possible to define an alias in most shells.  For bash and zsh, the following line will allow the usage of `smartless` when typing `less`.

    alias less='/path/to/smartless'

It can be useful to define an additional alias for jumping directly to the end of the input.  I like to call that alias `more`, but other more descriptive names are possible:

    alias more='/path/to/smartless +G'

## Configuration

Several optional environment variables control `smartless`.  These are described here, including their default values.

    # number of lines to directly display before entering  the pager
    SMARTLESS_NUM_LINES=15
    
    # the pager to be used
    SMARTLESS_PAGER='less'
    
    # the default arguments to the pager
    SMARTLESS_PAGER_ARGUMENTS='-iR --quiet'

## Contributing

Pull-request to improve `smartless` are welcomed.

## License

Copyright 2015 Stefan Heule

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
