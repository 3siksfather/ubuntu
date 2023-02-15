Ubuntu 인스턴스 20.04 이하 기준
SG에서 outbound 443포트 규칙 추가
(provo-mirror.opensuse.org : 91.193.113.70)

OS 정보를 쉘 변수 등록
source /etc/os-release

저장소를 추가
sudo sh -c "echo 'deb https://provo-mirror.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/ /' > /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list"

패키지 인증 키를 등록
wget -nv https://download.opensuse.org/repositories/devel:kubic:libcontainers:stable/xUbuntu_${VERSION_ID}/Release.key -O- | sudo apt-key add -

새 저장소의 패키지 목록을 업데이트
sudo apt update

podman을 설치
sudo apt -y install podman
