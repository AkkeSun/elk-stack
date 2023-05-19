# Filebeat Setup

> Filebeat 세팅 가이드 (CentOS)

Elastic Repository 추가를 위해 패키지 키를 불러옵니다.
```console
rpm --import https://packages.elastic.co/GPG-KEY-elasticsearch
```
yum repository 경로에 elastic repository를 추가합니다.

```console
# vi /etc/yum.repos.d/elastic.repo


[elastic-7.x]
name=Elastic repository for 7.x packages
baseurl=https://artifacts.elastic.co/packages/7.x/yum
gpgcheck=1
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
enabled=1
autorefresh=1
type=rpm-md
```

Filebeat를 설치 및 가동합니다.
```console
yum install filebeat
systemctl enable filebeat
chkconfig filebeat

# filebeat.yml 을 수정합니다
# 참고 : filebeat 는 한 번 추출된 데이터를 다시 추출하지 않습니다. 수정사항이 있을시 filebeat 디렉토리의 data 를 제거하세요
```

systemctl 커맨드로 filebeat를 조작할 수 있습니다.
```console
systemctl start filebeat
systemctl status filebeat
systemctl stop filebeat
```
<br/> 
<br/> 

> Filebeat 세팅 가이드 (MAC)
```
# 파일 다운로드
wget https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.17.10-darwin-x86_64.tar.gz

# 압축해제
tar -xvf [다운받은 파일명]
tar -xvf filebeat-7.17.10-darwin-x86_64.tar.gz
```