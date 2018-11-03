## AWS EC2 생성부터 SSH 연결까지 (windows)

- 인스턴스생성
    + (리전 확인)
    + Amazon Linux t2.micro
    + http 포트 개방
    + 하드 30GB
    + 키 페어 생성(~.pem)

- Elastic IP
    + 생성
    + 주소 연결
    + (인스턴스의 탄력적IP 확인)

- SSH 연결 (xShell 사용)
    + 새로 만들기
        * 호스트 : Elastic IP (ex. 13.209.42.592)
    + 사용자 : ec2-user <= (Amazon Linux 기준)
    + 사용자 키
        * 인스턴스 만들때 생성했던 .pem 가져오기
        * 암호 x

- root로 변경
    + sudo vi /etc/ssh/sshd_config
        * #PermitRootLogin yes => PermitRootLogin yes
    + $ sudo passwd root
    + $ 비밀번호 입력 (8 char 이상)
    + sudo mkdir /root/.ssh
    + sudo cp /home/ec2-user/.ssh/authorized_keys /root/.ssh
    + sudo service sshd restart Redirecting to /bin/systemctl restart sshd.service

- SSH 다시 연결
    + 사용자 ec2-user -> root 로 변경
    + 그 외에는 위와 동일

- yum 업데이트
    + sudo yum update
