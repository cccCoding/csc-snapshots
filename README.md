# csc-snapshots

[csc-20210902.zip](https://oneswap.oss-cn-hongkong.aliyuncs.com/csc-20210902.zip) (size 0.644GB)

MD5 checksum: 288521a01de6e657c8429c10e5b5bcb9

## Usage

Step 1: Preparation

* Make sure your hardware meets the suggested requirement.
* A disk with enough free storage, at least twice the size of the snapshot.

Step 2: Download && Uncompress

* Copy the above snapshot URL.
* Download: `wget -O csc.zip "{paste snapshot URL here}"` . It will take some time to download the snapshot, you can put it in the background by `nohup wget -O csc.zip "{paste snapshot URL here}" &`
* Uncompress: `unzip csc.zip`. It will take some time to uncompress, you can put it in the background by `nohup unzip csc.zip &`
* You can combine the above steps by running a script:
```shell
wget -O csc.zip "{paste snapshot URL here}"
unzip csc.zip
```

Step 3: Replace Data

* First, stop the running csc client if you have one by `kill {pid}`, and make sure the client has shut down.

* Consider backing up the original data: 

  ```shell
  mv ${CSC_DataDir}/cetd/chaindata ${CSC_DataDir}/cetd/chaindata_backup
  mv ${CSC_DataDir}/cetd/triecache ${CSC_DataDir}/cetd/triecache_backup
  ```

* Replace the data: 

  ```shell
  mv data/cetd/chaindata ${CSC_DataDir}/cetd/chaindata
  mv data/cetd/triecache ${CSC_DataDir}/cetd/triecache
  ```

* Start the csc client again and check the logs
