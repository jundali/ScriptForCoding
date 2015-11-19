# ScriptForCoding

#some useful script in linux

#convert the files from dos to unix
find  -name *.cpp *.h *.sh |xargs dos2unix

#convert the files from mac to dos
find  -name *.cpp *.h *.sh |xargs mac2unix
find  -name *.cpp *.h *.sh |xargs unix2dos

#find the files and copy to a folder
find -name *.qm |xargs -i cp {} /folderPath

#replace some string to other,for example replace a sql file
sed -e "s,string_old,string_new," old.sql > new.sql

#following are some useful script in windows

#set ip address auto config
netsh interface ip set address "Network Name" dhcp

#set ip address 
netsh interface ip set address name="Network Name" source=static 172.20.107.120 mask=255.255.255.0 gateway=172.20.107.254
netsh interface ip set dns "Network Name" static 172.20.1.110 

#clear the temp file before compile use vs
del /f/q *.user *.filters *.vcxproj *.pdb *.Debug *.Release *.sdf Makefile *.*bak *.bak
rd /S /Q debug
rd /S /Q release
rd /S /Q .vs

#clear the win7 system
@echo off 
color 0a
title 一键清理Win7系统垃圾清理(＾o＾)--www.x-berry.com
echo 清理垃圾文件，速度由电脑文件大小而定,在没看到结尾信息时 
echo 请勿关闭本窗口，您现在使用的是Win7系统垃圾一键清理工具。 
echo 正在清除系统垃圾文件，请稍后...... 
echo 删除补丁备份目录 
RD %windir%\$hf_mig$ /Q /S 
echo 把补丁卸载文件夹的名字保存成2950800.txt 
dir %windir%\$NtUninstall* /a:d /b >%windir%\2950800.txt 
echo 从2950800.txt中读取文件夹列表并且删除文件夹 
for /f %%i in (%windir%\2950800.txt) do rd %windir%\%%i /s /q 
echo 删除2950800.txt 
del %windir%\2950800.txt /f /q 
echo 删除补丁安装记录内容（下面的del /f /s /q %systemdrive%\*.log已经包含删除此类文件） 
del %windir%\KB*.log /f /q 
echo 删除系统盘目录下临时文件 
del /f /s /q %systemdrive%\*.tmp 
echo 删除系统盘目录下临时文件 
del /f /s /q %systemdrive%\*._mp 
echo 删除系统盘目录下日志文件 
del /f /s /q %systemdrive%\*.log 
echo 删除系统盘目录下GID文件(属于临时文件，具体作用不详) 
del /f /s /q %systemdrive%\*.gid 
echo 删除系统目录下scandisk（磁盘扫描）留下的无用文件 
del /f /s /q %systemdrive%\*.chk 
echo 删除系统目录下old文件 
del /f /s /q %systemdrive%\*.old 
echo 删除回收站的无用文件 
del /f /s /q %systemdrive%\recycled\*.* 
echo 删除系统目录下备份文件 
del /f /s /q %windir%\*.bak 
echo 删除应用程序临时文件 
del /f /s /q %windir%\prefetch\*.* 
echo 删除系统维护等操作产生的临时文件 
rd /s /q %windir%\temp md %windir%\temp 
echo 删除当前用户的COOKIE（IE） 
del /f /q %userprofile%\cookies\*.* 
echo 删除internet临时文件 
del /f /s /q "%userprofile%\local settings\temporary internet files\*.*" 
echo 删除当前用户日常操作临时文件 
del /f /s /q "%userprofile%\local settings\temp\*.*" 
echo 删除访问记录（开始菜单中的文档里面的东西） 
del /f /s /q "%userprofile%\recent\*.*"
echo.
echo. pause


