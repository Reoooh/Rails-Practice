# How to build Rbenv on manjaro

```bash
[reoh@reoh-manjaro ~]$ git clone https://github.com/rbenv/rbenv.git ~/.rbenv
正克隆到 '/home/reoh/.rbenv'...
remote: Enumerating objects: 2788, done.
remote: Total 2788 (delta 0), reused 0 (delta 0), pack-reused 2788
接收对象中: 100% (2788/2788), 536.25 KiB | 251.00 KiB/s, 完成.
处理 delta 中: 100% (1746/1746), 完成.
[reoh@reoh-manjaro ~]$ sudo pacman -S gcc make
[sudo] reoh 的密码：
警告：gcc-9.2.0-4 已经为最新 -- 重新安装
警告：make-4.2.1-4 已经为最新 -- 重新安装
正在解析依赖关系...
正在查找软件包冲突...

软件包 (2) gcc-9.2.0-4  make-4.2.1-4

全部安装大小：  146.09 MiB
净更新大小：    0.00 MiB

:: 进行安装吗？ [Y/n] 
(2/2) 正在检查密钥环里的密钥                       [##############] 100%
(2/2) 正在检查软件包完整性                         [##############] 100%
(2/2) 正在加载软件包文件                           [##############] 100%
(2/2) 正在检查文件冲突                             [##############] 100%
(2/2) 正在检查可用存储空间                         [##############] 100%
:: 正在处理软件包的变化...
(1/2) 正在重新安装 gcc                             [##############] 100%
(2/2) 正在重新安装 make                            [##############] 100%
:: 正在运行事务后钩子函数...
(1/2) Arming ConditionNeedsUpdate...
(2/2) Updating the info directory file...
[reoh@reoh-manjaro ~]$ cd ~/.rbenv && src/configure && make -C src
make: 进入目录“/home/reoh/.rbenv/src”
gcc -fPIC     -c -o realpath.o realpath.c
gcc -shared -Wl,-soname,../libexec/rbenv-realpath.dylib  -o ../libexec/rbenv-realpath.dylib realpath.o 
make: 离开目录“/home/reoh/.rbenv/src”

[reoh@reoh-manjaro .rbenv]$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile

[reoh@reoh-manjaro .rbenv]$ ~/.rbenv/bin/rbenv init
# Load rbenv automatically by appending
# the following to ~/.bash_profile:

eval "$(rbenv init -)"

[reoh@reoh-manjaro .rbenv]$ echo 'eval "$(rbenv init -)"' >> ~/.bash_profile

[reoh@reoh-manjaro .rbenv]$ source ~/.bash_profile

[reoh@reoh-manjaro .rbenv]$ curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash
curl: (7) Failed to connect to raw.githubusercontent.com port 443: 拒绝连接

[reoh@reoh-manjaro .rbenv]$ mkdir -p "$(rbenv root)"/plugins

[reoh@reoh-manjaro .rbenv]$ git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build
正克隆到 '/home/reoh/.rbenv/plugins/ruby-build'...
remote: Enumerating objects: 65, done.
remote: Counting objects: 100% (65/65), done.
remote: Compressing objects: 100% (50/50), done.
remote: Total 10193 (delta 38), reused 27 (delta 11), pack-reused 10128
接收对象中: 100% (10193/10193), 2.16 MiB | 138.00 KiB/s, 完成.
处理 delta 中: 100% (6626/6626), 完成.

[reoh@reoh-manjaro .rbenv]$ curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash
curl: (7) Failed to connect to raw.githubusercontent.com port 443: 拒绝连接

[reoh@reoh-manjaro .rbenv]$ rbenv versions
Warning: no Ruby detected on the system

[reoh@reoh-manjaro .rbenv]$ rbenv install 2.6.0
Downloading ruby-2.6.0.tar.bz2...
-> https://cache.ruby-lang.org/pub/ruby/2.6/ruby-2.6.0.tar.bz2
rInstalling ruby-2.6.0...
Installed ruby-2.6.0 to /home/reoh/.rbenv/versions/2.6.0

[reoh@reoh-manjaro .rbenv]$ rbenv versions
  2.6.0

[reoh@reoh-manjaro .rbenv]$ rbenv install -l
1.8.5-p52
1.8.5-p113
1.8.5-p114
1.8.5-p115
1.8.5-p231
1.8.6
1.8.6-p36
1.8.6-p110
1.8.6-p111
1.8.6-p114
1.8.6-p230
1.8.6-p286
1.8.6-p287
1.8.6-p368
1.8.6-p369
1.8.6-p383
1.8.6-p388
1.8.6-p398
1.8.6-p399
1.8.6-p420
1.8.7-preview1
1.8.7-preview2
1.8.7-preview3
1.8.7-preview4
1.8.7
1.8.7-p17
1.8.7-p22
1.8.7-p71
1.8.7-p72
1.8.7-p160
1.8.7-p173
1.8.7-p174
1.8.7-p248
1.8.7-p249
1.8.7-p299
1.8.7-p301
1.8.7-p302
1.8.7-p330
1.8.7-p334
1.8.7-p352
1.8.7-p357
1.8.7-p358
1.8.7-p370
1.8.7-p371
1.8.7-p373
1.8.7-p374
1.8.7-p375
1.9.0-0
1.9.0-1
1.9.0-2
1.9.0-3
1.9.0-4
1.9.0-5
1.9.1-preview1
1.9.1-preview2
1.9.1-rc1
1.9.1-rc2
1.9.1-p0
1.9.1-p129
1.9.1-p243
1.9.1-p376
1.9.1-p378
1.9.1-p429
1.9.1-p430
1.9.1-p431
1.9.2-preview1
1.9.2-preview3
1.9.2-rc1
1.9.2-rc2
1.9.2-p0
1.9.2-p136
1.9.2-p180
1.9.2-p290
1.9.2-p318
1.9.2-p320
1.9.2-p326
1.9.2-p330
1.9.3-dev
1.9.3-preview1
1.9.3-rc1
1.9.3-p0
1.9.3-p105
1.9.3-p125
1.9.3-p194
1.9.3-p286
1.9.3-p327
1.9.3-p362
1.9.3-p374
1.9.3-p385
1.9.3-p392
1.9.3-p426
1.9.3-p429
1.9.3-p448
1.9.3-p484
1.9.3-p545
1.9.3-p547
1.9.3-p550
1.9.3-p551
2.0.0-dev
2.0.0-preview1
2.0.0-preview2
2.0.0-rc1
2.0.0-rc2
2.0.0-p0
2.0.0-p195
2.0.0-p247
2.0.0-p353
2.0.0-p451
2.0.0-p481
2.0.0-p576
2.0.0-p594
2.0.0-p598
2.0.0-p643
2.0.0-p645
2.0.0-p647
2.0.0-p648
2.1.0-dev
2.1.0-preview1
2.1.0-preview2
2.1.0-rc1
2.1.0
2.1.1
2.1.2
2.1.3
2.1.4
2.1.5
2.1.6
2.1.7
2.1.8
2.1.9
2.1.10
2.2.0-dev
2.2.0-preview1
2.2.0-preview2
2.2.0-rc1
2.2.0
2.2.1
2.2.2
2.2.3
2.2.4
2.2.5
2.2.6
2.2.7
2.2.8
2.2.9
2.2.10
2.3.0-dev
2.3.0-preview1
2.3.0-preview2
2.3.0
2.3.1
2.3.2
2.3.3
2.3.4
2.3.5
2.3.6
2.3.7
2.3.8
2.4.0-dev
2.4.0-preview1
2.4.0-preview2
2.4.0-preview3
2.4.0-rc1
2.4.0
2.4.1
2.4.2
2.4.3
2.4.4
2.4.5
2.4.6
2.4.7
2.4.8
2.4.9
2.5.0-dev
2.5.0-preview1
2.5.0-rc1
2.5.0
2.5.1
2.5.2
2.5.3
2.5.4
2.5.5
2.5.6
2.5.7
2.6.0-dev
2.6.0-preview1
2.6.0-preview2
2.6.0-preview3
2.6.0-rc1
2.6.0-rc2
2.6.0
2.6.1
2.6.2
2.6.3
2.6.4
2.6.5
2.7.0-dev
2.7.0-preview1
2.7.0-preview2
2.7.0-preview3
2.7.0-rc1
2.7.0-rc2
jruby-1.5.6
jruby-1.6.3
jruby-1.6.4
jruby-1.6.5
jruby-1.6.5.1
jruby-1.6.6
jruby-1.6.7
jruby-1.6.7.2
jruby-1.6.8
jruby-1.7.0-preview1
jruby-1.7.0-preview2
jruby-1.7.0-rc1
jruby-1.7.0-rc2
jruby-1.7.0
jruby-1.7.1
jruby-1.7.2
jruby-1.7.3
jruby-1.7.4
jruby-1.7.5
jruby-1.7.6
jruby-1.7.7
jruby-1.7.8
jruby-1.7.9
jruby-1.7.10
jruby-1.7.11
jruby-1.7.12
jruby-1.7.13
jruby-1.7.14
jruby-1.7.15
jruby-1.7.16
jruby-1.7.16.1
jruby-1.7.16.2
jruby-1.7.17
jruby-1.7.18
jruby-1.7.19
jruby-1.7.20
jruby-1.7.20.1
jruby-1.7.21
jruby-1.7.22
jruby-1.7.23
jruby-1.7.24
jruby-1.7.25
jruby-1.7.26
jruby-1.7.27
jruby-9.0.0.0.pre1
jruby-9.0.0.0.pre2
jruby-9.0.0.0.rc1
jruby-9.0.0.0.rc2
jruby-9.0.0.0
jruby-9.0.1.0
jruby-9.0.3.0
jruby-9.0.4.0
jruby-9.0.5.0
jruby-9.1.0.0-dev
jruby-9.1.0.0
jruby-9.1.1.0
jruby-9.1.2.0
jruby-9.1.3.0
jruby-9.1.4.0
jruby-9.1.5.0
jruby-9.1.6.0
jruby-9.1.7.0
jruby-9.1.8.0
jruby-9.1.9.0
jruby-9.1.10.0
jruby-9.1.11.0
jruby-9.1.12.0
jruby-9.1.13.0
jruby-9.1.14.0
jruby-9.1.15.0
jruby-9.1.16.0
jruby-9.1.17.0
jruby-9.2.0.0-dev
jruby-9.2.0.0
jruby-9.2.1.0-dev
jruby-9.2.1.0
jruby-9.2.3.0
jruby-9.2.4.0
jruby-9.2.4.1
jruby-9.2.5.0
jruby-9.2.6.0
jruby-9.2.7.0
jruby-9.2.8.0
jruby-9.2.9.0
maglev-1.0.0
maglev-1.1.0-dev
maglev-2.0.0-dev
mruby-dev
mruby-1.0.0
mruby-1.1.0
mruby-1.2.0
mruby-1.3.0
mruby-1.4.0
mruby-1.4.1
mruby-2.0.0
mruby-2.0.1
mruby-2.1.0
rbx-2.2.2
rbx-2.2.3
rbx-2.2.4
rbx-2.2.5
rbx-2.2.6
rbx-2.2.7
rbx-2.2.8
rbx-2.2.9
rbx-2.2.10
rbx-2.3.0
rbx-2.4.0
rbx-2.4.1
rbx-2.5.0
rbx-2.5.1
rbx-2.5.2
rbx-2.5.3
rbx-2.5.4
rbx-2.5.5
rbx-2.5.6
rbx-2.5.7
rbx-2.5.8
rbx-2.6
rbx-2.7
rbx-2.8
rbx-2.9
rbx-2.10
rbx-2.11
rbx-2.71828182
rbx-3.0
rbx-3.1
rbx-3.2
rbx-3.3
rbx-3.4
rbx-3.5
rbx-3.6
rbx-3.7
rbx-3.8
rbx-3.9
rbx-3.10
rbx-3.11
rbx-3.12
rbx-3.13
rbx-3.14
rbx-3.15
rbx-3.16
rbx-3.17
rbx-3.18
rbx-3.19
rbx-3.20
rbx-3.21
rbx-3.22
rbx-3.23
rbx-3.24
rbx-3.25
rbx-3.26
rbx-3.27
rbx-3.28
rbx-3.29
rbx-3.30
rbx-3.31
rbx-3.32
rbx-3.33
rbx-3.34
rbx-3.35
rbx-3.36
rbx-3.37
rbx-3.38
rbx-3.39
rbx-3.40
rbx-3.41
rbx-3.42
rbx-3.43
rbx-3.44
rbx-3.45
rbx-3.46
rbx-3.47
rbx-3.48
rbx-3.49
rbx-3.50
rbx-3.51
rbx-3.52
rbx-3.53
rbx-3.54
rbx-3.55
rbx-3.56
rbx-3.57
rbx-3.58
rbx-3.59
rbx-3.60
rbx-3.61
rbx-3.62
rbx-3.63
rbx-3.64
rbx-3.65
rbx-3.66
rbx-3.67
rbx-3.68
rbx-3.69
rbx-3.70
rbx-3.71
rbx-3.72
rbx-3.73
rbx-3.74
rbx-3.75
rbx-3.76
rbx-3.77
rbx-3.78
rbx-3.79
rbx-3.80
rbx-3.81
rbx-3.82
rbx-3.83
rbx-3.84
rbx-3.85
rbx-3.86
rbx-3.87
rbx-3.88
rbx-3.89
rbx-3.90
rbx-3.91
rbx-3.92
rbx-3.93
rbx-3.94
rbx-3.95
rbx-3.96
rbx-3.97
rbx-3.98
rbx-3.99
rbx-3.100
rbx-3.101
rbx-3.102
rbx-3.103
rbx-3.104
rbx-3.105
rbx-3.106
rbx-3.107
ree-1.8.7-2011.03
ree-1.8.7-2011.12
ree-1.8.7-2012.01
ree-1.8.7-2012.02
topaz-dev
truffleruby-1.0.0-rc10
truffleruby-1.0.0-rc11
truffleruby-1.0.0-rc12
truffleruby-1.0.0-rc13
truffleruby-1.0.0-rc14
truffleruby-1.0.0-rc15
truffleruby-1.0.0-rc16
truffleruby-1.0.0-rc2
truffleruby-1.0.0-rc3
truffleruby-1.0.0-rc5
truffleruby-1.0.0-rc6
truffleruby-1.0.0-rc7
truffleruby-1.0.0-rc8
truffleruby-1.0.0-rc9
truffleruby-19.0.0
truffleruby-19.1.0
truffleruby-19.2.0
truffleruby-19.2.0.1
truffleruby-19.3.0

[reoh@reoh-manjaro .rbenv]$ curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash
Checking for `rbenv' in PATH: /home/reoh/.rbenv/bin/rbenv
Checking for rbenv shims in PATH: OK
Checking `rbenv install' support: /home/reoh/.rbenv/plugins/ruby-build/bin/rbenv-install (ruby-build 20191205-4-gf04eb99)
Counting installed Ruby versions: 1 versions
Checking RubyGems settings: OK
Auditing installed plugins: OK

[reoh@reoh-manjaro .rbenv]$ rbenv install 2.6.5
Downloading ruby-2.6.5.tar.bz2...
-> https://cache.ruby-lang.org/pub/ruby/2.6/ruby-2.6.5.tar.bz2
Installing ruby-2.6.5...
Installed ruby-2.6.5 to /home/reoh/.rbenv/versions/2.6.5

[reoh@reoh-manjaro .rbenv]$ rbenv versions
  2.6.0
  2.6.5

[reoh@reoh-manjaro .rbenv]$ rbenv install 2.3.8
Downloading ruby-2.3.8.tar.bz2...
-> https://cache.ruby-lang.org/pub/ruby/2.3/ruby-2.3.8.tar.bz2
Installing ruby-2.3.8...

BUILD FAILED (ManjaroLinux 18.1.4 using ruby-build 20191205-4-gf04eb99)

Inspect or clean up the working tree at /tmp/ruby-build.20191223221103.30168.cYoUjL
Results logged to /tmp/ruby-build.20191223221103.30168.log

Last 10 log lines:
make[1]: *** [exts.mk:212：ext/openssl/all] 错误 2
make[1]: *** 正在等待未完成的任务....
linking shared-object date_core.so
make[2]: 离开目录“/tmp/ruby-build.20191223221103.30168.cYoUjL/ruby-2.3.8/ext/date”
linking shared-object objspace.so
make[2]: 离开目录“/tmp/ruby-build.20191223221103.30168.cYoUjL/ruby-2.3.8/ext/objspace”
linking shared-object nkf.so
make[2]: 离开目录“/tmp/ruby-build.20191223221103.30168.cYoUjL/ruby-2.3.8/ext/nkf”
make[1]: 离开目录“/tmp/ruby-build.20191223221103.30168.cYoUjL/ruby-2.3.8”
make: *** [uncommon.mk:203：build-ext] 错误 2

[reoh@reoh-manjaro .rbenv]$ rbenv versions
  2.6.0
  2.6.5

[reoh@reoh-manjaro .rbenv]$ rbenv install 2.3.0
Downloading ruby-2.3.0.tar.bz2...
-> https://cache.ruby-lang.org/pub/ruby/2.3/ruby-2.3.0.tar.bz2
Installing ruby-2.3.0...

BUILD FAILED (ManjaroLinux 18.1.4 using ruby-build 20191205-4-gf04eb99)

Inspect or clean up the working tree at /tmp/ruby-build.20191223222214.8956.DJhCHS
Results logged to /tmp/ruby-build.20191223222214.8956.log

Last 10 log lines:
make[1]: *** [exts.mk:206：ext/openssl/all] 错误 2
make[1]: *** 正在等待未完成的任务....
linking shared-object objspace.so
make[2]: 离开目录“/tmp/ruby-build.20191223222214.8956.DJhCHS/ruby-2.3.0/ext/objspace”
linking shared-object pathname.so
make[2]: 离开目录“/tmp/ruby-build.20191223222214.8956.DJhCHS/ruby-2.3.0/ext/pathname”
linking shared-object nkf.so
make[2]: 离开目录“/tmp/ruby-build.20191223222214.8956.DJhCHS/ruby-2.3.0/ext/nkf”
make[1]: 离开目录“/tmp/ruby-build.20191223222214.8956.DJhCHS/ruby-2.3.0”
make: *** [uncommon.mk:203：build-ext] 错误 2

[reoh@reoh-manjaro .rbenv]$ rbenv install -l
1.8.5-p52
1.8.5-p113
1.8.5-p114
1.8.5-p115
1.8.5-p231
1.8.6
1.8.6-p36
1.8.6-p110
1.8.6-p111
1.8.6-p114
1.8.6-p230
1.8.6-p286
1.8.6-p287
1.8.6-p368
1.8.6-p369
1.8.6-p383
1.8.6-p388
1.8.6-p398
1.8.6-p399
1.8.6-p420
1.8.7-preview1
1.8.7-preview2
1.8.7-preview3
1.8.7-preview4
1.8.7
1.8.7-p17
1.8.7-p22
1.8.7-p71
1.8.7-p72
1.8.7-p160
1.8.7-p173
1.8.7-p174
1.8.7-p248
1.8.7-p249
1.8.7-p299
1.8.7-p301
1.8.7-p302
1.8.7-p330
1.8.7-p334
1.8.7-p352
1.8.7-p357
1.8.7-p358
1.8.7-p370
1.8.7-p371
1.8.7-p373
1.8.7-p374
1.8.7-p375
1.9.0-0
1.9.0-1
1.9.0-2
1.9.0-3
1.9.0-4
1.9.0-5
1.9.1-preview1
1.9.1-preview2
1.9.1-rc1
1.9.1-rc2
1.9.1-p0
1.9.1-p129
1.9.1-p243
1.9.1-p376
1.9.1-p378
1.9.1-p429
1.9.1-p430
1.9.1-p431
1.9.2-preview1
1.9.2-preview3
1.9.2-rc1
1.9.2-rc2
1.9.2-p0
1.9.2-p136
1.9.2-p180
1.9.2-p290
1.9.2-p318
1.9.2-p320
1.9.2-p326
1.9.2-p330
1.9.3-dev
1.9.3-preview1
1.9.3-rc1
1.9.3-p0
1.9.3-p105
1.9.3-p125
1.9.3-p194
1.9.3-p286
1.9.3-p327
1.9.3-p362
1.9.3-p374
1.9.3-p385
1.9.3-p392
1.9.3-p426
1.9.3-p429
1.9.3-p448
1.9.3-p484
1.9.3-p545
1.9.3-p547
1.9.3-p550
1.9.3-p551
2.0.0-dev
2.0.0-preview1
2.0.0-preview2
2.0.0-rc1
2.0.0-rc2
2.0.0-p0
2.0.0-p195
2.0.0-p247
2.0.0-p353
2.0.0-p451
2.0.0-p481
2.0.0-p576
2.0.0-p594
2.0.0-p598
2.0.0-p643
2.0.0-p645
2.0.0-p647
2.0.0-p648
2.1.0-dev
2.1.0-preview1
2.1.0-preview2
2.1.0-rc1
2.1.0
2.1.1
2.1.2
2.1.3
2.1.4
2.1.5
2.1.6
2.1.7
2.1.8
2.1.9
2.1.10
2.2.0-dev
2.2.0-preview1
2.2.0-preview2
2.2.0-rc1
2.2.0
2.2.1
2.2.2
2.2.3
2.2.4
2.2.5
2.2.6
2.2.7
2.2.8
2.2.9
2.2.10
2.3.0-dev
2.3.0-preview1
2.3.0-preview2
2.3.0
2.3.1
2.3.2
2.3.3
2.3.4
2.3.5
2.3.6
2.3.7
2.3.8
2.4.0-dev
2.4.0-preview1
2.4.0-preview2
2.4.0-preview3
2.4.0-rc1
2.4.0
2.4.1
2.4.2
2.4.3
2.4.4
2.4.5
2.4.6
2.4.7
2.4.8
2.4.9
2.5.0-dev
2.5.0-preview1
2.5.0-rc1
2.5.0
2.5.1
2.5.2
2.5.3
2.5.4
2.5.5
2.5.6
2.5.7
2.6.0-dev
2.6.0-preview1
2.6.0-preview2
2.6.0-preview3
2.6.0-rc1
2.6.0-rc2
2.6.0
2.6.1
2.6.2
2.6.3
2.6.4
2.6.5
2.7.0-dev
2.7.0-preview1
2.7.0-preview2
2.7.0-preview3
2.7.0-rc1
2.7.0-rc2
jruby-1.5.6
jruby-1.6.3
jruby-1.6.4
jruby-1.6.5
jruby-1.6.5.1
jruby-1.6.6
jruby-1.6.7
jruby-1.6.7.2
jruby-1.6.8
jruby-1.7.0-preview1
jruby-1.7.0-preview2
jruby-1.7.0-rc1
jruby-1.7.0-rc2
jruby-1.7.0
jruby-1.7.1
jruby-1.7.2
jruby-1.7.3
jruby-1.7.4
jruby-1.7.5
jruby-1.7.6
jruby-1.7.7
jruby-1.7.8
jruby-1.7.9
jruby-1.7.10
jruby-1.7.11
jruby-1.7.12
jruby-1.7.13
jruby-1.7.14
jruby-1.7.15
jruby-1.7.16
jruby-1.7.16.1
jruby-1.7.16.2
jruby-1.7.17
jruby-1.7.18
jruby-1.7.19
jruby-1.7.20
jruby-1.7.20.1
jruby-1.7.21
jruby-1.7.22
jruby-1.7.23
jruby-1.7.24
jruby-1.7.25
jruby-1.7.26
jruby-1.7.27
jruby-9.0.0.0.pre1
jruby-9.0.0.0.pre2
jruby-9.0.0.0.rc1
jruby-9.0.0.0.rc2
jruby-9.0.0.0
jruby-9.0.1.0
jruby-9.0.3.0
jruby-9.0.4.0
jruby-9.0.5.0
jruby-9.1.0.0-dev
jruby-9.1.0.0
jruby-9.1.1.0
jruby-9.1.2.0
jruby-9.1.3.0
jruby-9.1.4.0
jruby-9.1.5.0
jruby-9.1.6.0
jruby-9.1.7.0
jruby-9.1.8.0
jruby-9.1.9.0
jruby-9.1.10.0
jruby-9.1.11.0
jruby-9.1.12.0
jruby-9.1.13.0
jruby-9.1.14.0
jruby-9.1.15.0
jruby-9.1.16.0
jruby-9.1.17.0
jruby-9.2.0.0-dev
jruby-9.2.0.0
jruby-9.2.1.0-dev
jruby-9.2.1.0
jruby-9.2.3.0
jruby-9.2.4.0
jruby-9.2.4.1
jruby-9.2.5.0
jruby-9.2.6.0
jruby-9.2.7.0
jruby-9.2.8.0
jruby-9.2.9.0
maglev-1.0.0
maglev-1.1.0-dev
maglev-2.0.0-dev
mruby-dev
mruby-1.0.0
mruby-1.1.0
mruby-1.2.0
mruby-1.3.0
mruby-1.4.0
mruby-1.4.1
mruby-2.0.0
mruby-2.0.1
mruby-2.1.0
rbx-2.2.2
rbx-2.2.3
rbx-2.2.4
rbx-2.2.5
rbx-2.2.6
rbx-2.2.7
rbx-2.2.8
rbx-2.2.9
rbx-2.2.10
rbx-2.3.0
rbx-2.4.0
rbx-2.4.1
rbx-2.5.0
rbx-2.5.1Downloading ruby-2.3.0.tar.bz2...
rbx-2.5.2
rbx-2.5.3
rbx-2.5.4
rbx-2.5.5
rbx-2.5.6
rbx-2.5.7
rbx-2.5.8
rbx-2.6
rbx-2.7
rbx-2.8
rbx-2.9
rbx-2.10
rbx-2.11
rbx-2.71828182
rbx-3.0
rbx-3.1
rbx-3.2Downloading ruby-2.3.0.tar.bz2...
rbx-3.3
rbx-3.4
rbx-3.5
rbx-3.6
rbx-3.7
rbx-3.8
rbx-3.9
rbx-3.10
rbx-3.11
rbx-3.12
rbx-3.13
rbx-3.14
rbx-3.15
rbx-3.16
rbx-3.17
rbx-3.18
rbx-3.19
rbx-3.20
rbx-3.21Downloading ruby-2.3.0.tar.bz2...
rbx-3.22
rbx-3.23
rbx-3.24
rbx-3.25
rbx-3.26
rbx-3.27
rbx-3.28
rbx-3.29
rbx-3.30
rbx-3.31
rbx-3.32
rbx-3.33
rbx-3.34
rbx-3.35
rbx-3.36
rbx-3.37
rbx-3.38
rbx-3.39
rbx-3.40
rbx-3.41Downloading ruby-2.3.0.tar.bz2...
rbx-3.42
rbx-3.43
rbx-3.44
rbx-3.45
rbx-3.46
rbx-3.47
rbx-3.48
rbx-3.49
rbx-3.50
rbx-3.51
rbx-3.52
rbx-3.53
rbx-3.54
rbx-3.55
rbx-3.56
rbx-3.57
rbx-3.58
rbx-3.59
rbx-3.60
rbx-3.61
rbx-3.62
rbx-3.63
rbx-3.64
rbx-3.65
rbx-3.66
rbx-3.67
rbx-3.68
rbx-3.69
rbx-3.70
rbx-3.71
rbx-3.72
rbx-3.73
rbx-3.74
rbx-3.75
rbx-3.76
rbx-3.77
rbx-3.78
rbx-3.79
rbx-3.80
rbx-3.81
rbx-3.82
rbx-3.83
rbx-3.84
rbx-3.85
rbx-3.86
rbx-3.87
rbx-3.88
rbx-3.89
rbx-3.90
rbx-3.91
rbx-3.92
rbx-3.93
rbx-3.94
rbx-3.95
rbx-3.96
rbx-3.97
rbx-3.98
rbx-3.99
rbx-3.100
rbx-3.101
rbx-3.102
rbx-3.103
rbx-3.104
rbx-3.105
rbx-3.106
rbx-3.107
ree-1.8.7-2011.03
ree-1.8.7-2011.12
ree-1.8.7-2012.01
ree-1.8.7-2012.02
topaz-dev
truffleruby-1.0.0-rc10
truffleruby-1.0.0-rc11
truffleruby-1.0.0-rc12
truffleruby-1.0.0-rc13
truffleruby-1.0.0-rc14
truffleruby-1.0.0-rc15
truffleruby-1.0.0-rc16
truffleruby-1.0.0-rc2
truffleruby-1.0.0-rc3
truffleruby-1.0.0-rc5
truffleruby-1.0.0-rc6
truffleruby-1.0.0-rc7
truffleruby-1.0.0-rc8
truffleruby-1.0.0-rc9
truffleruby-19.0.0
truffleruby-19.1.0
truffleruby-19.2.0
truffleruby-19.2.0.1
truffleruby-19.3.0

[reoh@reoh-manjaro .rbenv]$ rbenv versions
  2.6.0
  2.6.5

[reoh@reoh-manjaro .rbenv]$ rbenv install 2.5.0
Downloading ruby-2.5.0.tar.bz2...
-> https://cache.ruby-lang.org/pub/ruby/2.5/ruby-2.5.0.tar.bz2
Installing ruby-2.5.0...
Installed ruby-2.5.0 to /home/reoh/.rbenv/versions/2.5.0

[reoh@reoh-manjaro .rbenv]$ rbenv versions
  2.5.0
  2.6.0
  2.6.5

[reoh@reoh-manjaro .rbenv]$ rbenv install 2.4.0
Downloading ruby-2.4.0.tar.bz2...
-> https://cache.ruby-lang.org/pub/ruby/2.4/ruby-2.4.0.tar.bz2
Installing ruby-2.4.0...
Installed ruby-2.4.0 to /home/reoh/.rbenv/versions/2.4.0

[reoh@reoh-manjaro .rbenv]$ rbenv versions
  2.4.0
  2.5.0
  2.6.0
  2.6.5

[reoh@reoh-manjaro .rbenv]$ ruby -v
rbenv: ruby: command not found

The `ruby' command exists in these Ruby versions:
  2.4.0
  2.5.0
  2.6.0
  2.6.5

[reoh@reoh-manjaro .rbenv]$ rbenv global 2.6.5

[reoh@reoh-manjaro .rbenv]$ ruby -v
ruby 2.6.5p114 (2019-10-01 revision 67812) [x86_64-linux]



```



```bash
[reoh@reoh-manjaro ~]$ gem -v
bash: gem：未找到命令
[reoh@reoh-manjaro ~]$ ruby -v
bash: ruby：未找到命令
[reoh@reoh-manjaro ~]$ rbenv -v
bash: rbenv：未找到命令
[reoh@reoh-manjaro ~]$ rbenv version
bash: rbenv：未找到命令
[reoh@reoh-manjaro ~]$ which ruby
which: no ruby in (/home/reoh/.local/bin:/usr/local/bin:/usr/local/sbin:/usr/bin:/usr/lib/jvm/default/bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl:/var/lib/snapd/snap/bin)
[reoh@reoh-manjaro ~]$ rbenv -v
bash: rbenv：未找到命令
[reoh@reoh-manjaro ~]$ which rbenv
which: no rbenv in (/home/reoh/.local/bin:/usr/local/bin:/usr/local/sbin:/usr/bin:/usr/lib/jvm/default/bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl:/var/lib/snapd/snap/bin)
[reoh@reoh-manjaro ~]$ code ~/.bashrc
[reoh@reoh-manjaro ~]$ clear

[reoh@reoh-manjaro ~]$ git clone https://github.com/rbenv/rbenv.git ~/.rbenv
fatal: 目标路径 '/home/reoh/.rbenv' 已经存在，并且不是一个空目录。
[reoh@reoh-manjaro ~]$ git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
fatal: 目标路径 '/home/reoh/.rbenv/plugins/ruby-build' 已经存在，并且不是一个空目录。
[reoh@reoh-manjaro ~]$ git clone git://github.com/jamis/rbenv-gemset.git  ~/.rbenv/plugins/rbenv-gemset
正克隆到 '/home/reoh/.rbenv/plugins/rbenv-gemset'...
remote: Enumerating objects: 502, done.
remote: Total 502 (delta 0), reused 0 (delta 0), pack-reused 502
接收对象中: 100% (502/502), 69.65 KiB | 171.00 KiB/s, 完成.
处理 delta 中: 100% (167/167), 完成.
[reoh@reoh-manjaro ~]$ git clone git://github.com/rkh/rbenv-update.git ~/.rbenv/plugins/rbenv-update
正克隆到 '/home/reoh/.rbenv/plugins/rbenv-update'...
remote: Enumerating objects: 242, done.
remote: Total 242 (delta 0), reused 0 (delta 0), pack-reused 242
接收对象中: 100% (242/242), 32.07 KiB | 132.00 KiB/s, 完成.
处理 delta 中: 100% (51/51), 完成.
[reoh@reoh-manjaro ~]$ git clone git://github.com/AndorChen/rbenv-china-mirror.git ~/.rbenv/plugins/rbenv-china-mirror
正克隆到 '/home/reoh/.rbenv/plugins/rbenv-china-mirror'...
remote: Enumerating objects: 86, done.
remote: Total 86 (delta 0), reused 0 (delta 0), pack-reused 86
接收对象中: 100% (86/86), 10.82 KiB | 65.00 KiB/s, 完成.
处理 delta 中: 100% (23/23), 完成.
[reoh@reoh-manjaro ~]$ code ~/.bash_profile
[reoh@reoh-manjaro ~]$ code ~/.bashrc
[reoh@reoh-manjaro ~]$ source ~/.bash_profile
[reoh@reoh-manjaro ~]$ rbenv install --list
1.8.5-p52
1.8.5-p113
1.8.5-p114
1.8.5-p115
1.8.5-p231
1.8.6
1.8.6-p36
1.8.6-p110
1.8.6-p111
1.8.6-p114
1.8.6-p230
1.8.6-p286
1.8.6-p287
1.8.6-p368
1.8.6-p369
1.8.6-p383
1.8.6-p388
1.8.6-p398
1.8.6-p399
1.8.6-p420
1.8.7-preview1
1.8.7-preview2
1.8.7-preview3
1.8.7-preview4
1.8.7
1.8.7-p17
1.8.7-p22
1.8.7-p71
1.8.7-p72
1.8.7-p160
1.8.7-p173
1.8.7-p174
1.8.7-p248
1.8.7-p249
1.8.7-p299
1.8.7-p301
1.8.7-p302
1.8.7-p330
1.8.7-p334
1.8.7-p352
1.8.7-p357
1.8.7-p358
1.8.7-p370
1.8.7-p371
1.8.7-p373
1.8.7-p374
1.8.7-p375
1.9.0-0
1.9.0-1
1.9.0-2
1.9.0-3
1.9.0-4
1.9.0-5
1.9.1-preview1
1.9.1-preview2
1.9.1-rc1
1.9.1-rc2
1.9.1-p0
1.9.1-p129
1.9.1-p243
1.9.1-p376
1.9.1-p378
1.9.1-p429
1.9.1-p430
1.9.1-p431
1.9.2-preview1
1.9.2-preview3
1.9.2-rc1
1.9.2-rc2
1.9.2-p0
1.9.2-p136
1.9.2-p180
1.9.2-p290
1.9.2-p318
1.9.2-p320
1.9.2-p326
1.9.2-p330
1.9.3-dev
1.9.3-preview1
1.9.3-rc1
1.9.3-p0
1.9.3-p105
1.9.3-p125
1.9.3-p194
1.9.3-p286
1.9.3-p327
1.9.3-p362
1.9.3-p374
1.9.3-p385
1.9.3-p392
1.9.3-p426
1.9.3-p429
1.9.3-p448
1.9.3-p484
1.9.3-p545
1.9.3-p547
1.9.3-p550
1.9.3-p551
2.0.0-dev
2.0.0-preview1
2.0.0-preview2
2.0.0-rc1
2.0.0-rc2
2.0.0-p0
2.0.0-p195
2.0.0-p247
2.0.0-p353
2.0.0-p451
2.0.0-p481
2.0.0-p576
2.0.0-p594
2.0.0-p598
2.0.0-p643
2.0.0-p645
2.0.0-p647
2.0.0-p648
2.1.0-dev
2.1.0-preview1
2.1.0-preview2
2.1.0-rc1
2.1.0
2.1.1
2.1.2
2.1.3
2.1.4
2.1.5
2.1.6
2.1.7
2.1.8
2.1.9
2.1.10
2.2.0-dev
2.2.0-preview1
2.2.0-preview2
2.2.0-rc1
2.2.0
2.2.1
2.2.2
2.2.3
2.2.4
2.2.5
2.2.6
2.2.7
2.2.8
2.2.9
2.2.10
2.3.0-dev
2.3.0-preview1
2.3.0-preview2
2.3.0
2.3.1
2.3.2
2.3.3
2.3.4
2.3.5
2.3.6
2.3.7
2.3.8
2.4.0-dev
2.4.0-preview1
2.4.0-preview2
2.4.0-preview3
2.4.0-rc1
2.4.0
2.4.1
2.4.2
2.4.3
2.4.4
2.4.5
2.4.6
2.4.7
2.4.8
2.4.9
2.5.0-dev
2.5.0-preview1
2.5.0-rc1
2.5.0
2.5.1
2.5.2
2.5.3
2.5.4
2.5.5
2.5.6
2.5.7
2.6.0-dev
2.6.0-preview1
2.6.0-preview2
2.6.0-preview3
2.6.0-rc1
2.6.0-rc2
2.6.0
2.6.1
2.6.2
2.6.3
2.6.4
2.6.5
2.7.0-dev
2.7.0-preview1
2.7.0-preview2
2.7.0-preview3
2.7.0-rc1
2.7.0-rc2
jruby-1.5.6
jruby-1.6.3
jruby-1.6.4
jruby-1.6.5
jruby-1.6.5.1
jruby-1.6.6
jruby-1.6.7
jruby-1.6.7.2
jruby-1.6.8
jruby-1.7.0-preview1
jruby-1.7.0-preview2
jruby-1.7.0-rc1
jruby-1.7.0-rc2
jruby-1.7.0
jruby-1.7.1
jruby-1.7.2
jruby-1.7.3
jruby-1.7.4
jruby-1.7.5
jruby-1.7.6
jruby-1.7.7
jruby-1.7.8
jruby-1.7.9
jruby-1.7.10
jruby-1.7.11
jruby-1.7.12
jruby-1.7.13
jruby-1.7.14
jruby-1.7.15
jruby-1.7.16
jruby-1.7.16.1
jruby-1.7.16.2
jruby-1.7.17
jruby-1.7.18
jruby-1.7.19
jruby-1.7.20
jruby-1.7.20.1
jruby-1.7.21
jruby-1.7.22
jruby-1.7.23
jruby-1.7.24
jruby-1.7.25
jruby-1.7.26
jruby-1.7.27
jruby-9.0.0.0.pre1
jruby-9.0.0.0.pre2
jruby-9.0.0.0.rc1
jruby-9.0.0.0.rc2
jruby-9.0.0.0
jruby-9.0.1.0
jruby-9.0.3.0
jruby-9.0.4.0
jruby-9.0.5.0
jruby-9.1.0.0-dev
jruby-9.1.0.0
jruby-9.1.1.0
jruby-9.1.2.0
jruby-9.1.3.0
jruby-9.1.4.0
jruby-9.1.5.0
jruby-9.1.6.0
jruby-9.1.7.0
jruby-9.1.8.0
jruby-9.1.9.0
jruby-9.1.10.0
jruby-9.1.11.0
jruby-9.1.12.0
jruby-9.1.13.0
jruby-9.1.14.0
jruby-9.1.15.0
jruby-9.1.16.0
jruby-9.1.17.0
jruby-9.2.0.0-dev
jruby-9.2.0.0
jruby-9.2.1.0-dev
jruby-9.2.1.0
jruby-9.2.3.0
jruby-9.2.4.0
jruby-9.2.4.1
jruby-9.2.5.0
jruby-9.2.6.0
jruby-9.2.7.0
jruby-9.2.8.0
jruby-9.2.9.0
maglev-1.0.0
maglev-1.1.0-dev
maglev-2.0.0-dev
mruby-dev
mruby-1.0.0
mruby-1.1.0
mruby-1.2.0
mruby-1.3.0
mruby-1.4.0
mruby-1.4.1
mruby-2.0.0
mruby-2.0.1
mruby-2.1.0
rbx-2.2.2
rbx-2.2.3
rbx-2.2.4
rbx-2.2.5
rbx-2.2.6
rbx-2.2.7
rbx-2.2.8
rbx-2.2.9
rbx-2.2.10
rbx-2.3.0
rbx-2.4.0
rbx-2.4.1
rbx-2.5.0
rbx-2.5.1
rbx-2.5.2
rbx-2.5.3
rbx-2.5.4
rbx-2.5.5
rbx-2.5.6
rbx-2.5.7
rbx-2.5.8
rbx-2.6
rbx-2.7
rbx-2.8
rbx-2.9
rbx-2.10
rbx-2.11
rbx-2.71828182
rbx-3.0
rbx-3.1
rbx-3.2
rbx-3.3
rbx-3.4
rbx-3.5
rbx-3.6
rbx-3.7
rbx-3.8
rbx-3.9
rbx-3.10
rbx-3.11
rbx-3.12
rbx-3.13
rbx-3.14
rbx-3.15
rbx-3.16
rbx-3.17
rbx-3.18
rbx-3.19
rbx-3.20
rbx-3.21
rbx-3.22
rbx-3.23
rbx-3.24
rbx-3.25
rbx-3.26
rbx-3.27
rbx-3.28
rbx-3.29
rbx-3.30
rbx-3.31
rbx-3.32
rbx-3.33
rbx-3.34
rbx-3.35
rbx-3.36
rbx-3.37
rbx-3.38
rbx-3.39
rbx-3.40
rbx-3.41
rbx-3.42
rbx-3.43
rbx-3.44
rbx-3.45
rbx-3.46
rbx-3.47
rbx-3.48
rbx-3.49
rbx-3.50
rbx-3.51
rbx-3.52
rbx-3.53
rbx-3.54
rbx-3.55
rbx-3.56
rbx-3.57
rbx-3.58
rbx-3.59
rbx-3.60
rbx-3.61
rbx-3.62
rbx-3.63
rbx-3.64
rbx-3.65
rbx-3.66
rbx-3.67
rbx-3.68
rbx-3.69
rbx-3.70
rbx-3.71
rbx-3.72
rbx-3.73
rbx-3.74
rbx-3.75
rbx-3.76
rbx-3.77
rbx-3.78
rbx-3.79
rbx-3.80
rbx-3.81
rbx-3.82
rbx-3.83
rbx-3.84
rbx-3.85
rbx-3.86
rbx-3.87
rbx-3.88
rbx-3.89
rbx-3.90
rbx-3.91
rbx-3.92
rbx-3.93
rbx-3.94
rbx-3.95
rbx-3.96
rbx-3.97
rbx-3.98
rbx-3.99
rbx-3.100
rbx-3.101
rbx-3.102
rbx-3.103
rbx-3.104
rbx-3.105
rbx-3.106
rbx-3.107
ree-1.8.7-2011.03
ree-1.8.7-2011.12
ree-1.8.7-2012.01
ree-1.8.7-2012.02
topaz-dev
truffleruby-1.0.0-rc10
truffleruby-1.0.0-rc11
truffleruby-1.0.0-rc12
truffleruby-1.0.0-rc13
truffleruby-1.0.0-rc14
truffleruby-1.0.0-rc15
truffleruby-1.0.0-rc16
truffleruby-1.0.0-rc2
truffleruby-1.0.0-rc3
truffleruby-1.0.0-rc5
truffleruby-1.0.0-rc6
truffleruby-1.0.0-rc7
truffleruby-1.0.0-rc8
truffleruby-1.0.0-rc9
truffleruby-19.0.0
truffleruby-19.1.0
truffleruby-19.2.0
truffleruby-19.2.0.1
truffleruby-19.3.0
[reoh@reoh-manjaro ~]$ rbenv version
2.6.5 (set by /home/reoh/.rbenv/version)
[reoh@reoh-manjaro ~]$ rbenv -v
rbenv 1.1.2-11-gc46a970
[reoh@reoh-manjaro ~]$ rbenv versions
  2.4.0
  2.5.0
  2.6.0
* 2.6.5 (set by /home/reoh/.rbenv/version)
[reoh@reoh-manjaro ~]$ rbenv which irb
/home/reoh/.rbenv/versions/2.6.5/bin/irb
[reoh@reoh-manjaro ~]$ rbenv whence irb
2.4.0
2.5.0
2.6.0
2.6.5
[reoh@reoh-manjaro ~]$ gem -v
3.0.3

```



We could find how to build rbenv in those website:
https://github.com/rbenv/rbenv#how-it-works
https://ruby-china.org/wiki/rbenv-guide
https://www.jianshu.com/p/1130e93687f2



虽然顺利地安装成功，但是开启新的terminal或者重启电脑后，rbenv依然无法被找到

显然还是有哪里不对

这涉及到了bash_profile与bashrc间的区别

