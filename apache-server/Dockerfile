FROM mcr.microsoft.com/windows/servercore:ltsc2019

# Install Chocolatey
RUN @powershell -NoProfile -ExecutionPolicy Bypass \
    -Command "$env:ChocolateyUseWindowsCompression='false';\
    iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" \
    && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"

# install Apache HTTP Server
RUN choco install -y apache-httpd --params '"/installLocation:C:\Apache /port:8088"'

# setup SSL for web server
WORKDIR /
COPY ./apache_conf/httpd.conf /Apache/conf/
COPY ./apache_conf/httpd-ssl.conf /Apache/conf/extras/

# copy certs
# TBD

# setup sample website
COPY ./site/ /Apache/htdocs/

SHELL ["ping", "-t", "localhost"]

ENTRYPOINT ["cmd"]
