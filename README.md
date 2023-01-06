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

---
### 正規表現
| code | content |
| --- | --- |
| . | 任意の1文字 |
| * | 直前の文字の0回以上の繰り返し |
| [] | []内のいずれか1文字(-：範囲、^：除外) |
| ^ | 行頭 |
| $ | 行末 |
| \ | 次の1文字をエスケープ |
| + | 直前の文字の1回以上の繰り返し(拡張正規表現) |
| ? | 直前の文字の0回もしくは1回の繰り返し(拡張正規表現) |
| \ |  |

---
### dpkg
設定ファイル /etc/dpkg/dpkg.cfg

| action | content |
| --- | --- |
| -i (--install) | インストール |
| -r (--remove) | 設定ファイルを残してアンインストール |
| -P (--purge) | 完全にアンインストール |
| -l (--list) | インストール済みパッケージを検索 |
| -S (--search) | ファイルがどのパッケージからインストールされたか表示 |
| -L (--listFfiles) | 指定パッケージからインストールされたファイル一覧を表示 |
| -s (--status) | パッケージ情報を表示する |
| --configure | 展開されたパッケージを構成 |
| --unpack | パッケージを展開(インストールしない) |

| option | content |
| --- | --- |
| -E | 同バージョンがインストールされていればインストールしない |
| -G | 新バージョンがインストールされていればインストールしない |
| -R (--recursive) | 再帰処理 |

---
### apt-get
| subcommand | content |
| --- | --- |
| clean | パッケージファイルを削除 |
| dist-upgrade | システムを最新にアップグレード |
| install | パッケージをインストールまたはアップグレード |
| remove | パッケージをアンインストール |
| update | パッケージデータベースを更新 |
| upgrade | 他のパッケージを削除しないものをアップグレード |

| option | content |
| --- | --- |
| -d | ファイルをダウンロード(インストールしない) |
| -s | システムを変更せず動作をシミュレート |

---
### apt-cache
| subcommand | content |
| --- | --- |
| search | キーワードを含むパッケージを検索 |
| show | パッケージの一般的な情報を表示 |
| showpkg | パッケージの詳細情報を表示 |
| depends | パッケージの依存関係を表示 |

---
## **apt**
設定ファイル /etc/apt/apt/conf.d/
ソース /etc/apt/sources.list
| subcommand | content |
| --- | --- |
| update | パッケージリストを更新 |
| install | パッケージをインストール |
| remove | 設定ファイルを残してパッケージを削除 |
| purge | パッケージを完全に削除 |
| upgrade | システムをアップグレード(ファイル削除は行わない) |
| full-upgrade | システムのメジャーバージョンを最新にアップグレード |
| show | 指定したパッケージに関する情報を表示 |
| list | パッケージのリストを表示 |
| list --installed | インストールされたパッケージを一覧表示 |
| list --upgradable | アップグレード可能なパッケージを表示 |
| search | 指定したキーワードでパッケージ情報を全文検索 |
| depends | パッケージの依存関係を表示 |
| autoremove | 必須とされていないパッケージを自動削除 |

| option | content |
| --- | --- |
| -C | 設定ファイルを指定 |
| -d | パッケージのダウンロードのみ行う |
| -y | 自動的にyesを回答 |
| --no-install-reccomends | 必須でない推奨パッケージはインストールしない |
| --install-suggests | 提案パッケージもインストール |
| --reinstall | インストール済みパッケージの再インストールを許可 |

---
## **rpm**
設定ファイル /usr/lib/rpm/rpmrc
| option | suboption | content |
| --- | --- | --- |
| -i (--install) |  | パッケージをインストール |
| -U (--upgrade) |  | パッケージをアップグレード(なければインストール) |
| -F (--freshen) |  | パッケージがインストールされていればアップグレード |
|  | -v | 詳細な情報を表示 |
|  | -h (--hash) | 進行状況を「#」で表示 |
|  | --nodeps | 依存関係を無視してインストール |
|  | --force | 既存のファイルを新しいものに置き換える |
|  | --test | 実際にはインストールせずテスト |
| -e (--erase) |  | パッケージをアンインストール |
|  | --nodeps | 依存関係を無視してアンインストール |
| -q |  | 指定したパッケージがインストールされているか照会 |
|  | -a (--all) | インストール済みのすべてのパッケージを表示 |
|  | -f | 指定したファイルを含むパッケージ名を表示 |
|  | -p | 対象としてパッケージファイルを指定 |
|  | -c (--configfiles) | 設定ファイルのみ表示 |
|  | -d (--docfiles) | ドキュメントのみ表示 |
|  | -i (--info) | 指定したパッケージの情報を表示 |
|  | -l (--list) | 指定したパッケージに含まれるファイルを表示 |
|  | -R (--requires) | 指定したパッケージが依存しているファイル等を表示 |
|  | --changelog | 変更履歴を表示 |

---
## **yum**
設定ファイル /etc/yum.confパッケージ取得元 /etc/yum.repos.d/
| subcommand | content |
| --- | --- |
| check-update | アップデート対象のパッケージリストを表示 |
| update | 指定したパッケージをアップデート(指定しない場合は全パッケージ) |
| install | 指定したパッケージをインストール |
| remove | 指定したパッケージをアンインストール |
| info | 指定したパッケージの情報を表示 |
| list | 全パッケージ情報をリスト表示 |
| repolist | リポジトリ一覧を表示 |
| search | パッケージ情報をキーワード検索 |
| search all | キーワード検索(パッケージ名、説明文等すべて) |
| groups list | パッケージグループをリスト表示 |
| graoups install | 指定したグループのパッケージをインストール |

---
## **dnf**
| subcommand | content |
| --- | --- |
| check-update | アップデート対象のパッケージリストを表示 |
| clean | キャッシュデータを削除 |
| upgrade (update) | システムの全パッケージをアップグレード |
| upgrade | 指定したパッケージをアップグレード |
| install | 指定したパッケージをインストール |
| remove | 指定したパッケージをアンインストール |
| info | 指定したパッケージの情報を表示 |
| list | 全パッケージ情報をリスト表示 |
| search | パッケージ情報をキーワード検索 |
| history | 処理の履歴を表示 |
| updateinfo | パッケージのアップデート情報を表示 |

