Cwm-recovery中文源码

本人开源个人Recovery项目，也希望各位用到我的代码的时候能提到我的名字，多谢

作者：Changyuet

感谢xiaolu大大提供汉化字库支持，感谢Xs的MTK备份方案，感谢CM团队

源码说明

BOARD_RECOVERY_MTK := true #65xx调用MTK平台备份源码,不添加此配置则调用默认备份源码

TARGET_RECOVERY_PIXEL_FORMAT := "RGBA_8888" #67xx颜色配置

通用配置:
RECOVERY_USE_MIGRATED_STORAGE := true #强制使用/data/media/0作为/sdcard，非必需

RECOVERY_USE_VIRTUAL_KEY := true #使用虚拟按键，非必需

KERNEL_EXFAT_MODULE_NAME := "exfat" #内核exfat模块名称，用于挂载exfat格式扩展，非必需，需要修改版vold

KERNEL_NTFS_MODULE_NAME := "ntfs" #内核exfat模块名称，用于挂载ntfs格式扩展，非必需，需要修改版vold

COMMON_GLOBAL_CFLAGS += -DNO_SECURE_DISCARD #修复双清缓慢，非必需

COMMON_GLOBAL_CFLAGS += -DQCOM_HARDWARE #加上这个选项会使用QCOM的时间修复

字库名中含有"fontcn"，会自动使用中文资源编译:
1920x1080
BOARD_USE_CUSTOM_RECOVERY_FONT := \"fontcn46_28x73.h\"
2560x1440
BOARD_USE_CUSTOM_RECOVERY_FONT := \"fontcn60_36x87.h\"

编译时把相应分辨率的virtual_key_res/virtual_keys_xxx.png拷贝到配置目录recovery/res/images/下，并改名为virtual_keys.png

例如device/samsung/klte/recovery/res/images/virtual_keys.png

