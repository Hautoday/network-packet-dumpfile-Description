### 라즈베리파이 네트워크 패킷 덤프 추출법.

- **해당 부분은 tcpdump가 설치가 안되어있을떄를 가정함**

```bash
sudo apt update
sudo apt install tcpdump 
```

1. apt의 선행 업데이트를 진행 후 제대로 업데이트 및 설치가 되었는지 확인한다. 
2. 이후 `sudo apt install tcpdump` 명령어를 통해 tcpdump 프로그램을 설치한다.

- 주로 통신하는 IP ( wlan0, eth0) 를 확인하기위해 ip를 확인한다.

```bash
linux -> ifconfig 
window -> ipconfig 
```

- 패킷 수집방법.
1. [ … ] → 해당 부분은 선택하여 작성하면 됨.
2. 본인의 ip를 확인하였다면, wifi를 사용하는지 랜선을 사용하는지에 따라 달라진다. 

```bash
sudo tcpdump -i [wlan0 or eth0] -w 파일명.pcap
```

실시간 확인이 필요한경우 명령어가 달라진다. 

```bash
sudo tcpdump -i [wlan0 or eth0] -n
```

- 저장된 파일 확인

```bash
ls -lh
# 방금 저장한 .pcap 파일의 용량이 0이 아니라면 성공
```


* 추후 안드로이드에서의 네트워크 패킷의 dump파일 추출에 관한 내용을 서술할 예정임. 
* 파킷 파일 분석에 대한 프로그램은 Wireshark 사용을 권고함.
