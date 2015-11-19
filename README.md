##ScriptForCoding##

###some useful script in linux###

###convert the files from dos to unix###
find  -name *.cpp *.h *.sh |xargs dos2unix

###convert the files from mac to dos###
find  -name *.cpp *.h *.sh |xargs mac2unix
find  -name *.cpp *.h *.sh |xargs unix2dos

###find the files and copy to a folder###
find -name *.qm |xargs -i cp {} /folderPath

###replace some string to other,for example replace a sql file###
sed -e "s,string_old,string_new," old.sql > new.sql

###following are some useful script in windows###

###set ip address auto config###
netsh interface ip set address "Network Name" dhcp

###set ip address ###
netsh interface ip set address name="Network Name" source=static 172.20.107.120 mask=255.255.255.0 gateway=172.20.107.254
netsh interface ip set dns "Network Name" static 172.20.1.110 

###clear the temp file before compile use visual studio###
del /f/q *.user *.filters *.vcxproj *.pdb *.Debug *.Release *.sdf Makefile *.*bak *.bak
rd /S /Q debug
rd /S /Q release
rd /S /Q .vs




