---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-14"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# 베어메탈 서버에 ISO 마운트

## 개요

대부분의 {{site.data.keyword.Bluemix_notm}} 고객이 서버와 함께 제공되는 표준 운영 체제 중 하나를 사용하지만 서버에 사용자 정의 ISO(디스크 이미지)를 마운트할 수 있습니다. 세 가지의 사용자 정의 ISO 마운트 옵션이 있습니다.

이 방법을 사용하려면 SL VPN 서비스(예: https://vpn.ams01.softlayer.com/ ) 또는 네트워크에 이미 연결된 다른 서버를 통해 사설 네트워크에 연결해야 합니다.

## 옵션 1(권장): IPMI 사용(CIFS 공유의 ISO)

이미 인프라를 {{site.data.keyword.Bluemix_notm}}에 배치한 경우, CIFS 공유를 내부 네트워크에 제공하도록 기존 서버를 구성할 수 있습니다. 그런 다음 베어메탈 서버에 임의의 ISO를 마운트할 수 있습니다.

이 방법은 로컬 네트워크를 통해 설치하므로 매우 빠르고, 로그아웃하거나 관리 인프라와 연결이 끊어진 경우에도 ISO가 마운트된 상태를 유지할 수 있으므로 베어메탈 서버에 사용자 정의 OS를 설치할 때 권장되는 방법입니다.

다음 단계에 따라 CIFS 공유에서 사용자 정의 OS를 설치하십시오.

1. ISO를 CIFS 공유에 배치하십시오.
* control.softlayer.com에서 지정된 IP로 웹 브라우저를 지정하고 디바이스 -> 서버(디바이스 세부사항) -> 원격 관리 아래에서 IPMI 관리 콘솔에 로그인하십시오. 사용자 이름 및 비밀번호도 여기에서 지정됩니다.
* **가상 미디어** 위로 마우스를 이동하고 **CD-ROM 이미지**를 클릭하십시오.
* 적절한 세부사항을 채우고 **저장 및 마운트**를 클릭하십시오.
* 모든 사용자가 서버의 BIOS를 변경할 수 있는 권한을 갖는 것은 아닙니다. 필요한 경우 다음 요청을 지원하는 티켓을 열 수 있습니다.
  * (가상 미디어 접속 모드를 변경할 수 있도록) IPMI에 대한 루트 사용자 관리자 권한이 필요합니다.
  * 'IPMI 가상 디스크'를 부팅 순서의 첫 번째 옵션으로 변경합니다.
* 이러한 변경이 수행된 후에 IPMI 관리 콘솔로 다시 돌아가서 구성 -> 원격 세션으로 이동하여 접속 모드를 **접속**으로 변경하십시오. 일부 오래된 IPMI 콘솔에서는 이 옵션을 건너뛸 수 있습니다.
* 서버를 다시 부팅하고 가상 미디어에서 부팅하십시오.


## 옵션 2: IPMIView 사용(CIFS 공유의 ISO)

전제조건:<br/>
* 부트 가능한 ISO가 있습니다.
* 부트 가능한 ISO를 저장하기 위한 Windows CIFS Server 또는 NAS 스토리지가 있습니다.
* ISO가 서버와 연관된 파일 스토리지(NAS)에 업로드됩니다.
* IPMIView가 설치되어 있거나 KVM 콘솔에 액세스합니다. <!--  * http://knowledgelayer.softlayer.com/procedure/download-ipmiview
* http://knowledgelayer.softlayer.com/procedure/access-kvm-console -->
* wget를 사용하여 ISO 파일을 다운로드할 수 있습니다.
* 패키지에 대한 액세스 및 설치를 수행하고 마운트를 작성할 수 있는 권한이 있는 SSH 액세스가 있습니다.


### Linux 및 Windows
아래 단계에 따라 IPMIView를 사용하여 ISO를 마운트하십시오.
1. 지원 티켓을 통해 서버가 가상 CD-ROM을 첫 번째 디바이스로 부팅하도록 요청하십시오. 각 디바이스가 연관된 가상 CD-ROM에서 부팅되어야 합니다. OS를 설치한 후에 이 설정을 되돌릴 수 있습니다. 
* [VPN](http://www.softlayer.com/VPN-Access)에 VPN 연결을 설정하십시오. Microsoft Internet Explorer를 사용하는 경우, 신뢰할 수 있는 사이트 목록에 .softlayer.com을 포함시키고 JAVA를 최신 상태로 유지하십시오.
* ISO 미디어를 NAS 또는 Windows CIFS Server로 복사하십시오.
  * SSH를 사용하여 Linux Jumpbox에 연결하십시오.
  * NAS 공유를 Linux Jumpbox에 마운트하십시오.

        mkdir /mnt/nasmount
        mount -t cifs //NAS_SERVER_NAME_ORIP/SLN#####-2 -o username=SLN#####-2,
        password=NAS_STORAGE_PW,rw,nounix,iocharset=utf8,file_mode=0644,dir_mode=0755 /mnt/nasmount
  * 명령 매개변수 키 마운트:
        NAS_SERVER_NAME_ORIP = NAS 스토리지의 이름 또는 IP.
        /SLN#####-2 = NAS 스토리지에 연결할 사용자 이름 및 폴더 이름.
        NAS_STORAGE_PW = NAS 스토리지에 대한 비밀번호.
        /mnt/nasmount = NAS 스토리지를 마운트할 폴더.
  * 디렉토리를 새 NAS 마운트 폴더로 변경하십시오.
        cd /mnt/nasmount
  * wget을 사용하여 ISO 파일을 다운로드하십시오.
        wget http://www.linktoyouriso.com/isofilename.iso
  다운로드를 완료했음을 나타내는 확인 메시지가 표시됩니다.
* 여기에 IPMI 보기 다운로드:
      http://knowledgelayer.softlayer.com/procedure/download-ipmiview
* 관리 IP를 통해 서버에 연결하십시오.
      http://knowledgelayer.softlayer.com/procedure/log-ipmiview
      http://knowledgelayer.softlayer.com/procedure/view-ipmi-credentials
* 가상 미디어 탭을 여십시오.
* CD-ROM 이미지 연결 세부사항을 완료하십시오.
  *
    * 공유 호스트 = NAS 스토리지의 IP 주소. NAS 스토리지 서버 이름을 Ping하여 이 값을 찾을 수 있습니다. 예를 들면, 다음과 같습니다. 
    ```
    ping nas501.service.softlayer.com
    ```
    * 공유 이름 = NAS 스토리지의 사용자 이름
    * 이미지의 경로 = 다음 형식의 ISO 파일 이름:
          \NASusername\isoname.iso(예: \SLN123456\centos6.iso)
    * 사용자 = NAS 스토리지의 사용자 이름
    * 비밀번호 = NAS 스토리지의 비밀번호
* 서버를 다시 부팅하십시오.
* KVM 콘솔 보기를 여십시오.
* 시스템 프롬프트에 따라 부트 가능한 ISO를 부팅하십시오.
* OS를 설치하십시오.
* 가상 미디어를 마운트 해제하십시오.
* 서버를 다시 시작하십시오.

## 옵션 3: 로컬 컴퓨터에서 ISO 마운트
<a name="option3"></a>

Java iKVM 뷰어(콘솔)를 사용하여 로컬 컴퓨터에서 ISO를 마운트할 수 있습니다. 이렇게 하면 콘솔에 연결되어 있는 동안 ISO를 마운트할 수 있습니다. 설치가 진행되는 속도는 업로드 속도, 인터넷 연결의 대기 시간, Java 및 사용자의 컴퓨터 성능에 따라 다를 수 있습니다.

사용자가 서버에서 BIOS를 변경할 수 있는 권한이 없는 경우 다음 변경 요청을 지원하도록 티켓을 여십시오.
* (가상 미디어 접속 모드를 변경할 수 있도록) IPMI에 대한 루트 사용자 관리자 권한이 필요합니다.
* 'IPMI 가상 디스크'를 부팅 순서의 첫 번째 옵션으로 변경합니다. (ISO가 아직 마운트되지 않았으므로 지원이 지금 현재는 부트 디바이스 우선순위만 변경해야 합니다.)


1. control.softlayer.com에서 지정된 IP로 웹 브라우저를 지정하여 IPMI 관리 콘솔에 로그인하십시오.
* 디바이스 > 서버(디바이스 세부사항) > 원격 관리를 클릭하십시오. 사용자 이름 및 비밀번호를 지정하십시오.
* 구성 > 원격 세션을 클릭하고 접속 모드를 **접속**으로 변경하십시오. 일부 오래된 IPMI 콘솔에서는 이 옵션을 사용할 수 없으므로 건너뛸 수 있습니다.
* 시스템 > 시스템 정보를 클릭하여 시스템 정보 페이지로 돌아가십시오. 그러면 콘솔 창 아이콘이 표시됩니다. 
* 콘솔 아이콘을 클릭하여 콘솔을 여십시오. 모든 보안 경고를 승인하십시오.
* 콘솔이 연결되면 로그인 프롬프트가 표시됩니다.
* 가상 미디어 > 가상 스토리지를 클릭하십시오.
* **CD-ROM&ISO** 탭으로 이동하여 **논리 드라이브 유형** 아래에서 ISO 파일을 선택하십시오.
* **이미지 열기**를 클릭하여 로컬 컴퓨터에서 ISO를 선택하십시오.
* **플러그인**을 클릭하여 ISO를 가상 CD-ROM 드라이브에 삽입하십시오.
* **확인**을 클릭하십시오.
* 서버를 다시 부팅하고 **가상 CD-ROM 드라이브에서 부팅** 옵션을 사용하십시오. 부트 디바이스를 선택하려면 iKVM 뷰어에서 가상 키보드를 사용해야 합니다.

## 문제점 해결

* 모든 사용자가 가상 미디어를 마운트할 수 있는 기본 액세스 권한이 있는 것은 아닙니다. 권한 오류가 발생하는 경우, 루트 IPMI 사용자 권한을 업데이트하려면 지원 팀에 문의하십시오.
* ISO가 이미 마운트된 경우, **마운트된 디스크가 있습니다.**라는 텍스트와 함께 오류 메시지가 표시됩니다. 기존 디스크를 마운트 해제하고 새 ISO로 대체해야 합니다. 두 개의 ISO가 동시에 마운트되지 않을 수 있습니다.
* BIOS에서 부팅 순서를 변경하기 위해 지원 팀에 문의해야 할 수도 있습니다.
* ISO를 마운트할 때 PPTP VPN 대신 SSL VPN(http://vpn.softlayer.com) 을 사용하십시오. 일단 VPN 네트워크에 연결되면 IPMI 주소(https://<private-ip-IPMI-management>)를 통해 시스템의 IPMI에 액세스할 수도 있습니다.
* ISO에 대한 경로를 입력할 때 경로에 대해 UNC 이름 구문(Universal Naming Convention)을 사용하십시오. 예를 들어, 다음과 같습니다.
  ```
  \\<NAS username>\<isoname>.iso
  ```
