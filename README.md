
# bc-snapshots


### Data

[bc_data_202309.tgz](https://pub-10cd0733ed3540f1a5bd893cdcaf4027.r2.dev/data_20230916.tgz)

md5sum checksum: d21fe4f5bc84273e08fbab93fca19456



### Usage

Step 1: Preparation
- A disk with enough free storage, at least twice the size of the snapshot

Step 2: Download && Uncompress
- Copy the above snapshot URL
- Download:  `wget -O data.tgz "<paste snapshot URL here>"` . It will take several hours to download the snapshot, you can put it in the background by `nohup wget -O data.tgz "<paste snapshot URL here>" &`
- Uncompress: `tar -xvf data.tgz`. It will take several hours to uncompress. You can put it in the background by `nohup tar -xvf data.tgz &`
- You can combine the above steps by running a script:
```
wget -O data.tgz "<paste snapshot URL here>"
tar -xvf data.tgz
```

Step 3: Replace Data
- Stop the running bc node if you have one by `kill {pid}`, and make sure the node has shut down
- Consider backup the original data: `mv ${BC_Home_Dir}/data ${BC_Home_Dir}/data_bak`
- Replace the data: `mv <uncompressed data dir> ${BC_Home_Dir}/data`
- Start the bc node again and check the logs
