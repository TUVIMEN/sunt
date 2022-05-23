# sunt
A bash script for backing up files.

## Instalation
    install -m 755 sunt /usr/bin

## Usage

Example config of ~/.config/sunt

    SUNT_INDEX="/home/user/index"
    SUNT_ENCRYPT="gpg -c --cipher-algo AES256 -z 0 --batch --passphrase-file /home/user/pass"
    SUNT_DECRYPT="gpg -d --batch --passphrase-file /home/user/pass"
    SUNT_COMPRESS="xz -e9"
    SUNT_DECOMPRESS="unxz"
    SUNT_HASH="md5sum"
    SUNT_PATH="/media/sdb1"
    SUNT_DEST="user@192.168.1.104:/media/sdc1"

Add files to index

    cd /media/sdb1
    sunt a file/file1 file2
    sunt a -c file3

Upload files to remote

    sunt u file2 file3

Delete files from index
    
    sunt d file3

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
