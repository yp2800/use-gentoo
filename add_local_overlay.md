# 添加本地Overlay
最近为了安装genymotion案桌模拟器，在官方overlay里找到necromancy-overlay，但已经废弃，无法安装。  
辗转找到[Kelvin-Gentoo-Overlay](https://github.com/Kelvin-Ng/Kelvin-Gentoo-Overlay)，学习了下如何手动添加overlay，参考[Local_overlay](https://wiki.gentoo.org/wiki/Overlay/Local_overlay)
* git clone到目录kelvin，这个目录名字在[repo_name](https://github.com/Kelvin-Ng/Kelvin-Gentoo-Overlay/blob/master/profiles/repo_name)
    
        cd /var/lib/layman
        git clone https://github.com/Kelvin-Ng/Kelvin-Gentoo-Overlay kelvin
* 添加配置  
    查看/etc/portage/make.conf，可以看到配置文件是/var/lib/layman/make.conf（假如配置过layman）
    把目录/var/lib/layman/kelvin添加到/var/lib/layman/make.conf里
* 安装，一定要有安装依赖android-sdk-update-manager

        emerge -av genymotion
* 还有几个方式，比较正统，详情见[brother-overlay](https://github.com/stefan-langenmaier/brother-overlay)
* 其他说明  
    安装后需要执行
        
            /opt/android-sdk-update-manager/tools/android  
    如果报SSLPeerUnverified peer not authenticated，就打开Tools->Options,勾选Force那个，就可以了  
    选择安装'Android SDK Platform-tools'和'Android SDK Tools'就可以了  
    安装完成后打开genymotion的Setting，设置ADB为/opt/android-sdk-update-manager

* 最新版本的genymotion-bin(gentoo源里的2.9.0-r1)，不会自动安装android-sdk-update-manager，需要自己手动安装
        
