# XHProf module for Silverstripe

A Silverstripe module for facilitating profiling with _XHProf_.

Since the Silverstripe 3 release, Silverstripe's built-in profiling has been disabled (see [this thread](https://github.com/silverstripe/sapphire/pull/618)). Thus, this module has sprung out of neccesity for profiling in _Silverstripe 3_.

This is a fork from the [XHProf](https://github.com/facebook/xhprof) PHP compiler, open sourced by _Facebook_ in 2009. It has been amended for easy integration with Silverstripe as well as installation instructions in this readme.

## Requirements
- *nix environment (probably works on OSX as well)
- Silverstripe 3+    
_Would also work on older Silverstripe versions, but installation instructions need to be amended_

## Installation

_XHProf_ needs to be installed and running on your system for this module to work. Once _XHPprof_ has been installed, follow the following steps:

- Download this module, and place it in your Silverstripe root, calling it `xhprof`
- Edit `/framework/main.php`, adding the following lines at the very top (under `<?php`), and at the very bottom:    
`include "../xhprof/_includes/header.php";`    
`include "../xhprof/_includes/footer.php";`
- Now, when running your site, you should see a `Profiler output` link on the very bottom of your site

## Installing XHProf

On an *nix machine with PECL installed, follow this instruction:

- `[sudo] pecl config-set preferred_state beta`
- `[sudo ] pecl install xhprof`
- Once installed, add this to the end of your `php.ini` file:    

```
[xhprof]
extension=xhprof.so
xhprof.output_dir="/var/tmp/xhprof"`
```
_You might need to create the dirctory_

- For the graphs to work, you need to install _GraphViz_:    
`apt-get install graphviz`

## XHProf Resources

* A very good guide on profiling with XHProf:    
<http://techportal.inviqa.com/2009/12/01/profiling-with-xhprof/>
* Another tutorial:    
<http://net.tutsplus.com/tutorials/php/advanced-codeigniter-profiling-with-xhprof/>


## Other Solutions

Beyond _XHProf_ another PHP profiling solution would be using _xDebug_, combined with a visualizer, which would either be built-in to an IDE, or using the PHP-based _Webgrind_ web interface.




