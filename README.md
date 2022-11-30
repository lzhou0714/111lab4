# Hey! I'm Filing Here

This program creates a mini EXT2 file system which is mounted in the mnt folder
It has a root directory, a lost+found directory, a hello-world file, and a symlink
hello that points to hello-world.
## Building

to build and compile use
make

## Running

To run and mount

./ext2-create # run executable to create cs111-base.img
mkdir mnt
sudo mount -o loop cs111-base.img mnt # mount your filesystem, loop lets you use a file


output of `ls -ain` 
total 7
     2 drwxr-xr-x 3    0    0 1024 Nov 29 15:12 .
942298 drwxr-xr-x 5 1000 1000 4096 Nov 29 15:12 ..
    13 lrw-r--r-- 1 1000 1000   11 Nov 29 15:12 hello -> hello-world
    12 -rw-r--r-- 1 1000 1000   12 Nov 29 15:12 hello-world
    11 drwxr-xr-x 2    0    0 1024 Nov 29 15:12 lost+found

## Cleaning up

To unmount the filesystem, remove the mount directory, and clean up all binary files

sudo umount mnt # unmount the filesystem
rmdir mnt # delete the directory used for mounting