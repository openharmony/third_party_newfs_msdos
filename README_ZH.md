# third_party_newfs_msdos

#### 介绍
newfs_msdos是Fat32格式化工具。实现在设备上构建一个FAT12、FAT16或FAT32的文件OS（FAT）文件系统。  

命令格式：  

    newfs_msdos [-N] [-@ offset] [-A] [-B boot] [-C create-size]
		        [-F FAT-type] [-I VolumeID] [-L label]	[-O OEM]
		        [-S sector-size] [-T timestamp] [-a FAT-size] [-b block-size]
		        [-c cluster-size] [-e DirEnts]	[-f format] [-h	heads]
		        [-i info] [-k backup] [-m media] [-n FATs] [-o	hidden]
		        [-r reserved] [-s total] [-u track-size] special [disktype]
如果 special 不包含 / 并且未使用 -C，则假定它是设备名称，并且 /dev/ 被添加到名称以构造实际设备名称。 要处理当前目录中的文件，请使用 ./filename。  

参数选项如下：  
- N  ：不要创建文件系统：只需打印参数。
- -@ offset  ：在设备或文件中以字节为单位的指定偏移量处构建文件系统。 附加到偏移量的后缀 s、k、m、g（小写或大写）分别指定该数字以扇区、千字节、兆字节或千兆字节为单位。
- -A  ：尝试群集对齐根目录，对 SD 卡有用。
- -B boot  ：从文件中获取引导程序。
- -C create-size  ：创建具有指定大小的图像文件。 附加到大小的后缀字符被解释为 -@ 选项。该文件是通过截断具有相同名称的任何现有文件并将其调整为请求的大小来创建的。 如果文件系统支持稀疏文件，则占用的磁盘空间可能小于参数指定的大小。
- -F FAT-type  ：FAT类型(12/16/32)
- -I VolumeID  ：卷 ID，十进制或十六进制 (0x...) 格式的 32 位数字。
- -L label  ：卷标（最多 11 个字符）。 标签应仅包含在常规 DOS (8+3) 文件名中允许的那些字符。
- -O OEM  ：OEM 字符串（最多 8 个字符）。 默认为“BSD 4.4”。、
- -S sector-size  ：每个扇区的字节数。 可接受的值为 512 到 32768 范围内的 2 的幂。
- -T timestamp  ：创建文件系统，就好像当前时间是时间戳一样。 默认文件系统卷 ID 来自时间。timestamp 可以是路径名（其中时间戳来自该文件）或解释为自纪元以来的秒数的整数值。
- -a FAT-size  ：每个 FAT 的扇区数。
- -b block-size  ：文件系统块大小（每个簇的字节数）
- -c cluster-size  ：每个集群的扇区。 可接受的值为 1 到 128 范围内的 2 的幂。
- -e dirents  ：根目录的条目数（仅限 FAT12 和 FAT16）
- -f format  ：指定标准（软盘）格式。 八种标准格式是（以千字节为单位的容量）：160、180、320、360、720、1200、1440、2880。
- -h heads  ：驱动头数
- -i info  ：文件系统信息扇区的位置（仅限 FAT32）。 0xffff 值表示没有信息扇区。
- -k backup  ：备份引导扇区的位置（仅限 FAT32）。 0xffff 值表示没有备份扇区。
- -m media  ：媒体描述符（可接受的范围 0xf0 到 0xff）。
- -n FATs  ：FAT 的数量。 可接受的值为 1 到 16（含）。 默认值为 2。
- -o hidden  ：隐藏扇区数
- -r reserved  ：保留扇区数。
- -s total  ：文件系统大小。
- -u track-size  ：每个磁道的扇区数。  
  
#### 来源
1.  newfs_msdos是[freebsd/freebsd-src](https://github.com/freebsd/freebsd-src/tree/master/sbin/newfs_msdos)下的一个功能。  
2.  BSD提供的[使用手册](https://www.freebsd.org/cgi/man.cgi?query=newfs_msdos)。  
3.  可以到[freebsd-src](https://github.com/freebsd/freebsd-src.git)了解源代码。   





