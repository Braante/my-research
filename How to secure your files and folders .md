# How to secure your files and folders?

Before, you should have openssl on your laptop, if you are on Linux, you must have it.
On Windows, i don't know.

## How to encrypt a file ?

`openssl aes-256-cbc -a -salt -iter 5 -in [name file] -out [new name].enc`

## How to decrypt a file ?

`openssl aes-256-cbc -d -a -iter 5 -in [encrypted file name].enc -out [new name].tar.gz`

## How to encrypt a folder ?

`tar -cf tmpdata.tar [name folder] && gzip tmpdata.tar && openssl aes-256-cbc -a -salt -iter 5 -in tmpdata.tar.gz -out [new name folder].enc && rm -f tmpdata.tar.gz`

## How to decrypt a folder ?

`openssl aes-256-cbc -d -a -iter 5 -in [encrypted folder name] -out tmpdata.tar.gz && tar -xzf tmpdata.tar.gz && rm -f tmpdata.tar.gz`