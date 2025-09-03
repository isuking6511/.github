# 최강zl존

> CJ 올리브네트웍스 클라우드 웨이브 6기 팀 프로젝트

## Member

| [![민동일](https://github.com/DongilMin.png)](https://github.com/DongilMin) | [![심규선](https://github.com/gyuseon25.png)](https://github.com/gyuseon25) | [![김지호](https://github.com/isuking6511.png)](https://github.com/isuking6511) | [![장욱재](https://github.com/dfadsfa.png)](https://github.com/dfadsfa) | [![박소정](https://github.com/sojung102.png)](https://github.com/sojung102) |
| :---: | :---: | :---: | :---: | :---: |
| **민동일** | **심규선** | **김지호** | **장욱재** | **박소정** |

<img width="639" height="494" alt="스크린샷 2025-08-30 14 21 54" src="https://github.com/user-attachments/assets/4116044f-862b-48aa-bac7-13a4b1975c0b" />
<img width="815" height="419" alt="스크린샷 2025-08-30 14 22 22" src="https://github.com/user-attachments/assets/323898de-7179-4fde-b4a0-7fde79ba35f5" />
<img width="468" height="241" alt="스크린샷 2025-08-30 14 24 24" src="https://github.com/user-attachments/assets/7737403a-f46a-400c-956c-3335847f36b0" />
<img width="846" height="281" alt="스크린샷 2025-08-30 14 24 56" src="https://github.com/user-attachments/assets/eab3515b-ccc4-4218-bbc3-57edf77311c2" />
<img width="568" height="433" alt="스크린샷 2025-08-30 14 22 36" src="https://github.com/user-attachments/assets/3e953462-e8dd-485b-8d13-8fb76cf800bb" />
<img width="647" height="338" alt="스크린샷 2025-08-30 14 23 10" src="https://github.com/user-attachments/assets/40b3eaa9-7047-4091-a97c-49f067daa151" />
<img width="891" height="276" alt="스크린샷 2025-08-30 14 23 30" src="https://github.com/user-attachments/assets/8deeb054-d753-4473-b935-98fab946519a" />
<img width="849" height="372" alt="스크린샷 2025-08-30 14 23 40" src="https://github.com/user-attachments/assets/56219913-ebc1-47af-a105-3e80d7b8d5a4" />
<img width="735" height="433" alt="스크린샷 2025-08-30 14 23 56" src="https://github.com/user-attachments/assets/f667249c-a80a-492d-8f23-e628e7b79b27" />
올리브영 글로벌 확장을 위한 최적의 보안 인프라
📌 프로젝트 개요
프로젝트명: 올리브영 글로벌 확장을 위한 최적의 보안 인프라 구축
프로젝트 기간: 2024년 11월 - 12월 (8주)
팀명: 최강지존 (CJ올리브네트웍스 클라우드웨이브 6기 5팀)
팀장: 민동일

🎯 기획 배경
K-뷰티 글로벌 확장의 현실
올리브영 글로벌 성장 현황

189개국 외국인 고객 942만 건 결제 처리
싱가포르, 일본, 미국 시장 성공적 진출
K-뷰티 산업의 글로벌 리더십 확보

인프라 관점의 도전 과제

전 세계 트래픽 동시 처리 필요성
글로벌 사이버 위협 노출 증가
24/7 무중단 서비스 요구

증가하는 보안 위협
2024년 보안 현황

사이버 침해사고 매년 50% 증가 (KISA 보고서)
유통·리테일 업계 주요 공격 대상
평균 피해액 45억원 + 신뢰도 손실


💡 프로젝트 목표
핵심 과제 설정
1. 보안 (Security)

제로 트러스트 원칙 기반 설계
다층 방어 체계 구축
실시간 위협 탐지 및 자동 대응

2. 성능 (Performance)

올영세일 수준 트래픽 처리 (평소 10배)
글로벌 무중단 서비스 제공
2분 내 재해 복구 달성

3. 비용 (Cost)

스토리지 비용 최적화
자동 스케일링으로 리소스 효율화
태그 기반 비용 추적 관리


🏗️ 구현 아키텍처
하이브리드 클라우드 구성
온프레미스 환경

GitLab 서버를 격리된 사설망에 구축
VPC 피어링을 통한 보안 통신
소스코드 유출 원천 차단

AWS 클라우드 환경

EKS 기반 마이크로서비스 아키텍처 (MSA)
Karpenter를 통한 자동 스케일링
개발(Staging)과 운영(Production) 환경 완전 분리

재해복구(DR) 환경

도쿄 리전 웜 스탠바이 구성
RDS Aurora 실시간 복제
Route53 기반 2분 내 자동 전환


🔐 보안 구현
제로 트러스트 아키텍처
SPIRE 기반 mTLS 구현

60초 수명 초단기 인증서 발급
30초 주기 자동 갱신
플랫폼 독립적 신원 증명

다층 방어 체계

WAF를 통한 1차 방어
SPIRE/mTLS 서비스 간 통신 보안
Falco 컨테이너 런타임 보안

자동화된 보안 대응
외부 위협 대응

WAF 실시간 차단 규칙 적용
OpenSearch 대시보드 실시간 모니터링
Slack/Email 즉시 알림

내부 위협 방어

SonarQube 코드 취약점 자동 검사
시크릿 스캐너 비밀키 유출 차단
Falco 이상 행위 실시간 감지


⚡ 성능 최적화
자동 스케일링 구현
Karpenter 기반 확장

파드 자동 스케일링 (HPA)
노드 자동 프로비저닝
트래픽 감소 시 자동 축소

성능 향상 기술

Kafka 비동기 처리 도입
VPC Endpoint 네트워크 최적화
ARM 아키텍처 도입 (최대 40% 성능 향상)


💰 비용 최적화
스토리지 최적화
S3 수명주기 정책

자주 사용: Standard
30일 이후: Standard-IA
90일 이후: Glacier

비용 절감 결과

서울 리전 기준 44% 절감
올리브영 실제 규모 적용 시 54% 예상

리소스 최적화
시간대별 자동화

Lambda + EventBridge 심야 리소스 축소
태그 기반 비용 추적
불필요 리소스 자동 정리


📊 프로젝트 성과
보안 등급 향상

SSL Labs 평가: B등급 → A등급

성능 검증

올영세일 시나리오 부하테스트 통과
DR 전환 시간 2분 달성
대규모 트래픽 무중단 처리 확인

비용 효율성

스토리지 비용 44% 절감 달성
자동 스케일링으로 유휴 리소스 최소화
