# sunt

A bash script for backing up files.

## Installation
    install -m 755 sunt /usr/bin

## Usage

Example config of ~/.config/sunt

    SUNT_INDEX="/home/user3/index"
    SUNT_ENCRYPT="openssl enc -e -aes-256-cbc -salt -pbkdf2 -iter 1000000 -md sha512 -in /dev/stdin -pass file/home/user3/pass -out /dev/stdout"
    SUNT_DECRYPT="openssl enc -d -aes-256-cbc -salt -pbkdf2 -iter 1000000 -md sha512 -in /dev/stdin -pass file:/ome/user3/pass -out /dev/stdout"
    SUNT_COMPRESS="xz -e9"
    SUNT_DECOMPRESS="unxz"
    SUNT_HASH="sha256sum"
    SUNT_DEST="user1,ssh user1@192.168.1.104,/media/sdc1,/home/user3/d1,user2,ssh user2@192.168.1.105,/media/sdc2,/home/user3/d2"

Add files to index

    cd /media/sdb1
    sunt a file/file1 file2
    sunt a -c file3

Upload files to remote

    sunt u file2 file3

Delete files from index and on remote

    sunt d -r file3

Copy index file to remote

    sunt i

Add and upload files

    sunt au file4 file5
    sunt au -c file6/*.mp4

Restore files from remote

    sunt r file3
    sunt r -f file2

Show index file

    sunt l
