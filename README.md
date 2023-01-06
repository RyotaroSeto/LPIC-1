# LPIC-1
LPIC101-1の基本


### デバイスファイル
| device file | content |
| -------- | :----- |
| /dev/sda     | 1番目のハードディスクドライブ  | 
| /dev/sdb     | 2番目のハードディスクドライブ   |
| /dev/sdc     | 3番目のハードディスクドライブ   |
| /dev/sr0     | 1番目のCD/DVDドライブ   |
| /dev/st0     | 1番目のテープドライブ   |

---
### ファイルシステム
| filesystem | content |
| -------- | :----- |
| ext2    | 	Linuxの標準ファイルシステム  | 
| ext3     |  ext2にジャーナリング機能を追加  |
| ext4     |  	ext3を機能拡張  |
| XFS     |   SGI社が開発したジャーナリングファイルシステム |
| Btrfs     |  	高度な機能  |
| iso9660     |  	CD-ROM  |
| udf     |  	DVD-ROM  |

---
### ディレクトリ・ファイル
| path | content |
| --- | --- |
| /proc | 起動中のプロセスやカーネルが認識しているハードウェアの情報が格納されているディレクトリ |
| /proc/modules | ロードされているカーネルモジュールの情報 |
| /proc/cpuinfo | CPUに関する情報 |
| /proc/meminfo | メモリの使用状況を確認できるファイル |
| /proc/bus/usb/devices | USBデバイスに関する情報 |
| /proc/bus/pci/devices | PCIデバイスに関する情報 |
| /proc/interrupts | IRQに関する情報 |
| /proc/ioports | 	I/Oポートアドレスの情報 |
| /proc/dma | デバイスが使用中のDMAチャンネルに関する情報 |
| --- | --- |
| /proc/scsi/scsi | SCSIデバイスに関する情報 |
| /proc/cmdline | ブートローダからカーネルに渡されたパラメータ |
| /etc | システムの設定ファイルなどが格納されているディレクトリ |
| /etc/inittab |  |
| /etc/rc[0-6].d | SysVinitでランレベルに応じたスクリプトが格納されるディレクトリ |
| /etc/systemd/system/ |  |
| /etc/udev/rules.d/(~.rules) | udevが使用するデバイス設定情報 |
| /etc/modprobe.d/(~.conf) | modprobeの設定ファイル |
| /etc/default/grub | GRUB2の設定ファイル |
| /etc/grub.d | GRUB2の設定ファイルを配置するディレクトリ |
| /etc/ld.so.conf | ldconfigで/etc/ld.so.cacheを作成するために参照 |
| /etc/ld.so.cache | プログラムの実行時に共有ライブラリの場所を検索するために使用 |
| /etc/dpkg/dpkg.cfg | dpkgの設定ファイル |
| /etc/apt/apt/conf.d/ | aptの設定ファイル |
| /etc/apt/sources.list | aptのパッケージ取得元を設定するファイル |
| /etc/yum.conf | yumの設定ファイル |
| /etc/yum.repos.d | yumで使用されるパッケージの取得元を設定するファイルを格納するディレクトリ |
| /etc/machine-id | マシンIDが格納されているファイル |
| /etc/fstab | ファイルシステムのマウント設定を記載するファイル |
| /etc/mtab | 現在マウントされているファイルシステムの情報が格納されているファイル |
| /var |  |
| /var/log/messages | カーネルのログが記録されるなど、Linuxでメインで使用されるログファイル |
| /boot |  |
| /boot/efi | ESP(EFIシステムパーティション)のマウント先 |
| /boot/grub/menu.lst | GRUB Legacyの設定ファイル |
| /boot/grub/grub.conf | GRUB Legacyの設定ファイル |
| /boot/grub/grub.cfg | GRUB2の設定ファイル(変更不可) |
| /usr |  |
| /usr/share/man | マニュアル |

---
### vi

| command | content |
| --- | --- |
| ZZ | 保存して終了(:wq) |
| :e! | 最後に保存した内容に復帰 |
| :r ファイル名 | ファイルの内容をカレント行以降に読み込む |
| :!コマンド | viを終了せずにシェルコマンドを実行 |
| :r!コマンド | シェルコマンドの実行結果を挿入 |
| dw | カーソル位置から次の単語までを削除 |
| r | カーソル位置の1文字を置換 |
| :%s/A/B/ | 最初に見つかった文字列Aを文字列Bに置換 |
| :%s/A/B/g | 全ての文字列Aを文字列Bに置換 |
| :set nu (number) | 行番号を表示 |
| :set nonu (nonumber) | 行番号を非表示 |
| :set ts=タブ幅 (tabstop) | タブ幅を指定 |
