#### Windows 下 Mongodb 全量备份

```
@echo off
rem ----------------------------------------------------------------------
rem This is the mongodb backup script.
rem You can use this script to copy an other mongodb's data file. 
rem ----------------------------------------------------------------------

rem GetDate
rem  GetYear:%date:~0,4%GetMonth:%date:~5,2%:GetDay:%date:~8,2%

echo current date : %date%
set strYear=%date:~0,4%&set strMonth=%date:~5,2%&set strDay=%date:~8,2%
set strDate=%strYear%%strMonth%%strDay%

rem ----------------------------------------------------------------------
rem ----------------------Backup Start------------------------------------
echo ----------------------Backup Start-----------------------------------

rem 设置 mongodb 根目录
set MONGO_PATH=D:\gbros\mongodb
rem 设置 mongodb 备份目录名
set BACKUP_DIR_LOCAL=%MONGO_PATH%\backup\mongo_bak_%strDate%

rem 创建备份目录
echo Backup Dir 1 : %BACKUP_DIR_LOCAL%
mkdir %BACKUP_DIR_LOCAL%

rem 设置备份命令
set _EXECMONGODUMP=start %MONGO_PATH%\bin\mongodump.exe

rem 设置备份命令参数
set MONGODUMP_OPTS_LOCAL= --db ead --out %BACKUP_DIR_LOCAL%

rem 执行备份命令
echo ---------Backup Local------------
%_EXECMONGODUMP% %MONGODUMP_OPTS_LOCAL% 
echo ---------Backup Local Over-------

echo ---------------------------Backup Over-----------------------------------
rem ----------------------------Backup Over------------------------------------
rem ---------------------------------------------------------------------------

rem mongodb delete bak script
rem the script can delete backup fold 7 days before now day.
rem 指定待删除文件的存放路径
set SrcDir=D:\gbros\mongodb\backup\
rem 指定保留文件天数
set DaysAgo=7
  
>"%temp%/DstDate.vbs" echo LastDate=date()-%DaysAgo%
>>"%temp%/DstDate.vbs" echo FmtDate=right(year(LastDate),4) ^& right("0" ^& month(LastDate),2) ^& right("0" ^& day(LastDate),2)
>>"%temp%/DstDate.vbs" echo wscript.echo FmtDate
for /f %%a in ('cscript /nologo "%temp%/DstDate.vbs"') do (
  set "DstDate=%%a"
)
set DstDate=%DstDate:~0,4%%DstDate:~4,2%%DstDate:~6,2%

rem 设置删除路径
echo %DstDate%
set DEL_PATH=D:\gbros\mongodb\backup\mongo_bak_%DstDate%
  
echo Delete Local %DEL_PATH%
if exist %DEL_PATH% (rd /s /q %DEL_PATH%)

endlocal 

```