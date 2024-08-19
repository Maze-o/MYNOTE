<h2>Linux</h2>

LINUX OS 특징		
무료		
오픈소스 - 원하는 형태의 리눅스를 만들수 있다		
C언어로 만들었기때문에 플랫폼에 독립적 사용이 가능 (지금은 그닥 의미 없다. (미들웨어를 사용하기때문에))	 		

1. repo update		
sudo = 다른 계정으로 변경할때 사용(Root권한 사용)		
sudo apt update		
		
2. ssh Service install		
ssh service 다운로드		
sudo apt install openssh-server		
		
설치확인 - sudo systemctl status ssh		
sudo systemctl restart ssh			
		
3. 방화벽		
ufw - ubuntu firewall 약자		
sudo ufw allow ssh 		
		
sudo systemctl enable ssh - 자동으로 실행 될수 있도록		
		
Consolas 체 사용 권장				
		
			
		
user1@user1-VirtualBox:~$ 에서 ~(현재 작업위치) $(계정 구분기호) $(일반) #(관리자)			
sudo su - 관리자계정으로 전환		
passwd user1 user1의 비밀번호를 바꾸기 (관리자계정에서)			
		
ifconfig 쓰기 위해 apt install net-tools		
		
cp 		
-i 질의 -yes or no		
-r 디렉토리 복사		
-p 보존복사 		
		
