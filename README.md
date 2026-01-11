## OBC-SIM for GR740

 GR740 에뮬레이팅을 지원하지 않는 Renode에 기존 IP Core들을 이용하여 GR740 에뮬레이팅을 지원할 수 있는 .repl 파일을 제공합니다.

## Related Publication

**Automatic Fault Tolerance Management based on Task Criticality for Real-Time Systems**  
Minwoo Kang, Hunkyu Maeng, Hyeonsoo Jeon, Junyong Park, Jiwoo Shin, Jinman Jung

*The 41st ACM/SIGAPP Symposium On Applied Computing, March 2026*

## 🚀 빠른 시작

### 1. 환경설정
우분투 환경을 가정하고 다음과 같이 진행합니다. 윈도우 사용자라면 아래 두가지 방법 중 하나를 통해 우분투 환경을 구성해주세요.

####   WSL

```powershell
wsl --install
```

####   Docker
- Docker 설치: https://www.docker.com/get-started/

- 우분투 이미지 다운로드
```powershell
docker pull ubuntu:22.04
```

- 우분투 컨테이너 생성
```powershell
docker run -it --name '컨테이너 이름' -v ${pwd}:/workspace ubuntu:22.04 /bin/bash
```

### 2. 패키지, 소스 코드 다운로드
```bash
cd /workspace

apt-get update

apt install -y git automake cmake autoconf libtool g++ coreutils policykit-1 libgtk-3-dev uml-utilities \
gtk-sharp3 python3 python3-pip dotnet-sdk-6.0

git clone https://github.com/OBC-SIM/OBC-SIM-for-GR740.git .
```

### 3.빌드
```bash
./build.sh
```

### 4.실행
```bash
./renode
```

```bash
### monitor
using sysbus
mach create
machine LoadPlatformDescription @platforms/cpus/gr740.repl
sysbus LoadELF @your application
start
```
