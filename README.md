# -Opsec 백서 한국어판-

---

<img src="Qubesosoverviewv2.jpg" style="width: 70%;">

<b>0. 익명성, 항상 침목과 자신과의 비밀을 존중, 실수 하지 않기, 무감정 상태 유지 
1. 노트북 또는 SBC, 기타 서브 컴퓨터 사용 (자신의 컴퓨터 절대 사용금지)
2. 공용 와이파이 사용, 노트북 Aircard 사용 또는 유료 VPN 이용
3. Windows 사용 금지 (Qubes, Whonix + Kali, Tails 사용)
4. "영어대소문자, 숫자, 특수기호"가 모두 포함된 16자리 이상 패스워드 사용
5. 무료 VPN 사용 금지, 유료 VPN 사용 (Mullvad, Proton, Tor)
6. 불법 행위를 하는 경우 소셜 미디어에 게시하거나 사진, 등을 찍는 흔적을 남지 않기.
7. 파일 내려 받을때 반드시 VirusTotal로 의심스러운 파일을 검사
8. 암호화 알고리즘이 사용된 VeraCrypt로 하드 암호화 (BitLocker 절대 사용 금지)
9. 프로그램 실행전 sandboxie 통한 가상화 사전 프로그램 실행
10. OS, VM 설치 할땐 암호화된 저장매체에 이용 (Nitrokey, Yubikey)
11. 2FA/MTA 구글 OTP 사용 금지 Authy 또는 Aegis OTP 사용
12. 암호 기록시 BitWarden 이용 
13. 하드, 등 기억장치를 빠르게 날릴수 있는 버튼 설정</b>

## Opsec 백서 2022 한국어 (made by anonmoinx)

[1. 기기 및 운영체제](#기기-및-운영체제)<p>
[2. 저장 매체 및 암호화](#저장-매체-및-암호화)<p>
[3. VPN](#VPN)<p>
[4. 파일 업로드](#파일-업로드)<p>
[5. 코인 거래시](#코인-거래시)<p>
[6. 대화 매체](#대화-매체)<p>
[7. 1회성 혹은 임시 이메일](#1회성-혹은-임시-이메일)<p>
[8. 이중 인증](#이중-인증)<p><p>


--- 
  
## 네트워크 

[IP 주소]<p>
<br>
IP 주소는 'whois' 조회를 통해 누가 소유하는지 확인할 수 있습니다.<p>
IP 주소 관리하는 곳에서 IP 주소를 위도/경도 위치로 전환할 수 있는 지리적 위치 데이터베이스가 있습니다.<p>
일반적으로 지리적 위치는 최소한 해당 IP 주소가 현재 연결된 ISP 데이터 센터로 연결됩니다.<p>
일반적으로 주거용 인터넷 소비자인 경우 해당 주소를 소유한 ISP를 볼 수 있고<p>
연방 정부는 주어진 시간에 해당 주소를 임대한 회사에 물어보기만 하면<p>
주거지의 특정 아파트 번호로 연결될 수 있기 때문 입니다.<p>
<br>
[Wi-Fi 및 Bluetooth]<p>
<br>
Wi-Fi 및 Bluetooth는 작동 중에 고유 식별자(MAC)를 유출 됩니다.<p>
항상 그렇지는 않지만 임의적이며 때로는 그렇지 않다.<p>
이러한 식별자는 근처 스니퍼에 의해 기록될 수 있으며<p>
이러한 스니퍼가 연결되면 사용자의 움직임에 대해서도 알 수 있습니다.<p>
<br>
이 문제를 해결할 방법은 현재 완전한 방법은 없으나,<p>
전문가 의견에 따르면 그렇다고 WIFI를 끄는 데에는 도움이 되지는 않는다.<p>
Wi-Fi를 켜고 케이블을 여기저기 끌지 않는 자유를 즐기세요.<p>
좋은 암호와 최신 암호화 알고리즘을 사용하고 <p>
기본 인터넷 액세스 등만 허용하도록 VLAN으로 액세스를 잠그라고 조언하였다.<p>
<br>
<b>현재 Bluetooth는 완화할 수 없으며 비활성화만 가능합니다(BLE 포함 - 별도의 설정임).</b><p>
모든 Wi-Fi 클라이언트는 알려진 모든 SSID(및 BSSID)를 브로드캐스트하여 근처 AP에 연결합니다.<p>
또한 모든 레거시 클라이언트에는 고유한 MAC이 있습니다. 따라서 다음을 수행해야 합니다.<p>
<br>
<b>- MAC주소 무작위 변경 (Qubes OS 지원)</b>
  
<b>- 네트워크 프로브의 MAC을 무작위로 지정하는 Android 9 이상 사용(빌드에 따라 개발자 설정에 있거나 없을 수 있음)</b>

<b>- AP를 가장 일반적인 AP로 설정 하고 정기적으로 스크립트(OpenWRT)를 사용하여 BSSID를 변경하면 AP 매핑에도 도움이 됩니다.</b>

후자의 대안은 자동 전환기를 사용하는 것입니다.

https://f-droid.org/en/packages/be.uhasselt.privacypolice/

https://f-droid.org/en/packages/net.kismetwireless.android.smarterwifimanager/

https://f-droid.org/en/packages/org.secuso.privacyfriendlywifimanager/
  
---

## 기기 및 운영체제

<b>자신의 컴퓨터는 절대 사용하면 안될것</b><p>
노트북 또는 X86 지원되는 SBC 사용한다.<p> 
<br>
ODYSSEY - X86J4105 (이 제품은 실제로 Qubes를 구현해낸 x86 SBC이다.)<p>
(https://www.seeedstudio.com/blog/2020/05/26/qubes-os-security-oriented-operating-system-and-run-qubes-os-on-odyssey-x86j4105/)<p>
ODROID - H3+ (이 제품은 최근이 나온 x86모델중 사양이 가장 좋다.)<p>
이외에도 라떼판다, RockPI 등이 있다.
<br>
노트북은 중고 제품 써도 된다. 그리 좋은 사양은 필요 없다.<p>
일반적으로 공용 와이파이를 사용하거나 AirCard 사용하는것이 좋다.<p> 
<br>
권장 OS는 Whonix, Qubes, Tails 이렇게 3가지 이다.<p>
보통 VM를 통해서 Whonix+Kali 환경을 사용하는 것을 추천한다.<p>
추가적으로 MAC주소 노출에 민감하다면 Qubes+Whonix 환경을 세팅하면된다.<p>
Qubes가 유일하게 MAC 주소 익명화를 제공하기 때문이다.<p>
https://github.com/Qubes-Community/Contents/blob/master/docs/privacy/anonymizing-your-mac-address.md<p>
윈도우는 절대 사용하지 말것.<p>
</br>

---
## 저장 매체 및 암호화
[저장매체]

Nitrokey Storage 2 (오픈소스 : 개인정보 수집을 하지 않기 때문) <p>
yubikey (오픈소스가 아님) <p>
기타 5 NFC가 활성화된 Bitwarden <p>
<br>
  
[디스크 암호화]
  

veracrypt 통해 디스크를 "완전한 암호"으로 암호화 한다.<p>
<br>
**안드로이드 (~2015)**

'안전한 비밀번호'로 잠금 설정 후

(기기마다 다름) 보안 > 디바이스 암호화<p>
<br>
**안드로이드 (2016~)**

'안전한 비밀번호'로 잠금 설정 후

(기기마다 다름) 보안 > 보안 시작 > 전원을 켤 때마다 설정<p>
<br>
**아이폰 (3GS~)**

'안전한 비밀번호'로

잠금 설정

하지만 컴퓨터나 휴대폰을 켜져 있는 동안 기기의 "메모리(RAM)에 비밀번호가 임시 저장"돼 있어,

"위기 순간" 이 오면 전원을 내린 후 RAM에 있는 것들이 날아갈 때까지 시간을 끄는 것 이 생존 가능성을 높이는 길입니다...
  
  
---
  
## VPN

mullvad VPN, Protonvpn 사용 한다. (무료 VPN은 절대 사용하면 안된다.)<p>
mullvad VPN은 모든 VPN 중 유일하게 정보 유출이 된 기록이 없다. <p>
https://mullvad.net/en/blog/2022/6/22/vpn-server-audit-found-no-information-leakage-or-logging-of-customer-data/<p>
<br>
(mullvad VPN는 제 3자를 통해 구입 하는것이 더욱 안전)<p>
https://digitalgoods.proxysto.re/<p>
<br>
실수로 잠시 동안 VPN을 사용하지 않으면<p>
때에 따라 다르지만, VPN을 켜고 웹사이트를 탐색 중<p>
"극비 익명 전자 메일 주소" 계정에 로그인한 기록이 브라우저 쿠키가 남을 수 있다.<p>
그러고 나서 VPN 연결을 끊으면 브라우저가 이 서버에 HTTP 요청하게 된다.<p>
<br> 
즉, 쿠키는 똑같이 해당 서버의 웹 사이트에서 보내지게 된다.<p>
그들은 당신의 쿠키가 독일에서 나온 것을 보았고, 그 다음에는 캐나다, 등 기타 국가<p>
그렇게 돌고돌아 당신의 "진짜 위치"가 어디에 있는지 볼수 있게 되는것이다.<p>
<br>
실크로드의 다크웹 마약 거래 플랫폼을 운영하던 사람이,<p>
실제 IP 주소 환경에서 IRC 계정에 로그인한 것 때문에 잡힌 것이다.<p>
그가 다크웹에서 그렇게 유명한 사업을 운영하고 있었기 때문에, 그의 계정들은 면밀히 감시되었고<p>
그가 한 번 실수로 인해 그의 진짜 IP 주소를 유출시킨 것이 그를 잡는데 도움이 되었다.<p>
<br>
  VPN을 사용하지 않고 모든 요청을 거부하는 <b>킬 스위치(Always On VPN)</b> 수단이 있어야 한다.<p>
터널링 절차 때문에 OpenVPN을 사용하면 쉽다. 필수는 아니지만 실제 IP를 유출하고 네트워크를 노출하지 않는것으로 적극 권장한다.<p>
또한 적절한 방화벽 규칙을 통해 네트워크에 연결하고 해당 VPN 호스트를 통해서만 인터넷에 연결할 수 있도록 구성한다.<p>
<br>
  <b>최적의 솔루션은 OpenVPN + Mullvad + Tor</b>
  
  

---


## 파일 업로드
<br>
대용량 CDN 파일 전송 (2주 무료) / 익명 이메일 사용<p>
[Bunny CDN | Hop on the Fastest Content Delivery Network!]<p>
(https://bunny.net)<p>
<br>
익명 파일 업로더<p>
[Anonymous File Upload]<p>
(https://anonfiles.com/)<p>
<br>
  
파일 바이러스 검사 (파일 내려받을때 검사 필수)<p>
[VirusTotal]
(https://www.virustotal.com/gui/home/upload)<p>


---
  
## 코인 거래시

XHV 또는 XMR(모네로) 사용<p>
<br>
[온라인 지갑]<p>
Railgun Aztec(zk.money)와 SCRT
[Overview - Safe](https://gnosis-safe.io/)<p>
<br>
[하드웨어 지갑]<p>
[Ledger](https://shop.ledger.com/products/ledger-nano-x?r=8b49b9c6f1fe&tracker=checklist),
[Trezor](https://shop.trezor.io/?offer_id=10&aff_id=1181)
  
---
  
## 대화 매체
IRC 기반 채널 채팅 (권장)<p>
<br>
Nicegram (텔레그램) 이용 (자기 번호 절대 금지)<p>
https://my.nicegram.app/login?lng=ko <p>


---
  
## 1회성 혹은 임시 이메일

Tutanota <p>
https://tutanota.com/ <p>
<br>
Protonmail <p>
https://proton.me/ <p>
<br>
가입 시 랜덤 아이디/패스워드 이용 (늘 사용하던건 금지) <p>

---
  
## 이중 인증 

SMS 기반 2FA, Google OTP 금지!! <p>
Authy 또는 Aegis OTP 사용

---
