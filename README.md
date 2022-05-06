# BTRFS SNAPSHOT

## PREPARE FILESYSTEM FOR SNAPSHOTS
- Needed requirements
 
  - BTRFS FILESYSTEM PARTITION
 
  - SUBVOLUME FOR SNAPSHOTS STORAGE

## REALIZE SNAPHSOT
- make snapshot
`$ sudo btrfs subvolume snapshot /example /.snapshots/example`

- view snapshot data info
`$ sudo btrfs subvolume show /.snapshots/example`

## RECOVER DATA LOST FROM THE SNAPSHOT DIRECTORY
`$ sudo rsync -avz /.snapshots/example/ /example(folder data lost)/`

## USEFULL MOUNT OPTIONS USED BRIEF EXPLANATION

 - noatime : No access time, Improves system performances by not writing time when the file was accesed

 - compress=zstd : Chosing the algorithm for compress. I have zstd as it has good compression level and speed
  
 - discard= async : ONLY USE IF YOU SYSTEM PARTITION IS MOUNTED ON A SSD DEVICE, enable discarding of freed file blocks improving performance

 - subvol : Choosing the subvol to mount.
 
 
