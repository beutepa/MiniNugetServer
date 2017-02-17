FROM microsoft/windowsservercore
RUN "powershell set-itemproperty -path 'HKLM:\SYSTEM\CurrentControlSet\Services\Dnscache\Parameters' -Name ServerPriorityTimeLimit -Value 0 -Type DWord"
RUN ["powershell","wget","http://nginx.org/download/nginx-1.10.2.zip","-UseBasicParsing","-OutFile","c:\\nginx.zip"]
RUN ["powershell","Expand-Archive","c:\\nginx.zip","-Dest","c:\\nginx"]
COPY nginx.conf c:/nginx/nginx-1.10.2/conf
WORKDIR c:\\nginx\\nginx-1.10.2
ENTRYPOINT ["powershell",".\\nginx.exe"]