# Margarita Shotgun

## Installing

`pip install git+git://github.com/joelferrier/margaritashotgun.git@develop`

## Usage

From the project root: `./bin/margarita-shotgun -h`


    usage: cli.py [-h] [-s SERVER] [-u USERNAME] [-p PASSWORD] [-k KEYFILE]
                  [-m MODULE] [-c CONFIG]
    
    optional arguments:
      -h, --help            show this help message and exit
      -s SERVER, --server SERVER
                            hostname or ip of target server
      -u USERNAME, --username USERNAME
                            username for ssh connection
      -p PASSWORD, --password PASSWORD
                            password user, or for encrypted keyfile when used with
                            -k argument
      -k KEYFILE, --keyfile KEYFILE
                            path to rsa key for ssh connection
      -m MODULE, --module MODULE
                            path to kernel lime kernel module
      -c CONFIG, --config CONFIG
                            path to config.yml

## Configuration

Margarita shotgun can be configured with a YAML formatted file passed in with the -c flag.  
  
To upload to s3 use the following format:  

    aws:
        bucket: mshotgun
        key:    <aws key id>
        secret: <aws secret key>
    hosts:
        - addr:     52.36.191.XXX
          port:     22
          username: ec2-user
          keyfile:  access.pem
          module:   lime-4.1.19-24.31.amzn1.x86_64.ko

To write to a local file exclude the aws section from configuration  

## Building

`python setup.py sdist` places build artifacts in `dist/`  

Install with `pip install dist/margarita_shotgun-0.1.0.tar.gz`  

## License

The MIT License (MIT)

Copyright (c) 2016 Joel Ferrier

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
