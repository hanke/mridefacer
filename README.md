# mridefacer
From the manpage:
````

Helper to aid de-identification of MRI images (3D or 4D).

A de-face mask image will be created for each input image, by aligning
template mask to the input. Optionally, de-face masks can be applied
to the input images to either replace the original image, or create
modified copies in a specified output directory.

This tool can process single or series of images. In the latter case,
the computed transformation between template image and input image will
be updated incrementally for the next image in the series. This feature
is most suitable for processing images that have been recorded in
temporal succession.

Note that any output images will comform the FSL's radiological image
orientation.


Usage:  mridefacer [OPTIONS] <imagefile> [<imagefile> [...]]


Options:

--apply
  If this flag is set, the defacing is applied to the input images.
  By default, defacing mask images are created only. If --outdir is
  not provided, the actual input images will be replaced by defaced
  versions. In this case, the resulting images will be in FSL's
  standard radiological orientation.

-h, --help
  Print short description, usage summary and option list.

--no-colored
  If set, mridefacer won't colorize its status and error messages.

--outdir
  If set, output files will be put into this directory. By default,
  output files are placed in the same directory as the respective input
  files.

--verbose
  Enable additional status messages.

--verbose-help
  Print all available help.

--version
  Print version information and exit.


Examples:

mridefacer ADMME
  Deface a single image

Environment:

mridefacer requires FSL and the environment variable FSLDIR needs to be set
accordingly. mridefacer acknowledges MRIDEFACER_DATA_DIR to determine the
location of the required MRI template images.


Report bugs to <michael.hanke@gmail.com>.

````

### Installation

- go to the directory where you want to save `mridefacer` and get it using:</br>
`cd path/where/mridefacer/should/be/stored` </br>
`git clone https://github.com/mih/mridefacer`
- add it to your `PATH` either temporary (using `export`)
`export PATH="$PATH:path/where/mridefacer/is/stored/"` </br>
- or permanently, setting it in your `profile` using your favorite editor:
`nano/vim/gedit/etc ~/.bashrc`or `nano/vim/gedit/etc ~/.bash_profile` to include the following:</br>
`PATH=$PATH:path/were/mridefacer/is/stored` </br>
- do the same `MRIDEFACER_DATA_DIR`

- check if your FSLDIR environment variable is set by typing `$FSLDIR` in your terminal and in case it is not set, do so by repeating the steps you did for `mridefacer`, adapting them to `FSLDIR` (that is, where `FSL` is stored on your machine):</br>
`export FSLDIR="path/where/FSL/is/stored"` </br>
or include it in your `profile`:</br>
`FSLDIR="path/where/FSL/is/stored"`

- after completing the above steps, `mridefacer` should work out-of-the-box in most cases

- in case you're receiving an error related to `numbound`, please install the `num-utils` package:</br>
`apt-get install num-utils`



Please note: mridefacer runs natively on [linux systems](https://en.wikipedia.org/wiki/Linux) such as [neurodebian](http://neuro.debian.net/) and [ubuntu](https://www.ubuntu.com/), but won't work on [macOS](https://en.wikipedia.org/wiki/MacOS) or [windows](https://en.wikipedia.org/wiki/Microsoft_Windows).
