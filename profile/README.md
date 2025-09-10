<div align="center">

# 🌐 Cloud Infrastructure for Global OliveYoung

> K-뷰티 리더 올리브영의 글로벌 확장을 위한 MSA 기반 제로 트러스트(Zero Trust) 보안 인프라

<p>
  <img src="https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/Terraform-7B42BC?logo=terraform&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Helm-0F1689?logo=helm&logoColor=white" />
</p>
<p>
  <img src="https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=white" />
  <img src="https://img.shields.io/badge/Java-007396?logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring-6DB33F?logo=spring&logoColor=white" />
  <img src="https://img.shields.io/badge/Apache%20Kafka-231F20?logo=apachekafka&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20DynamoDB-4053D6?logo=amazondynamodb&logoColor=white" />
</p>
<p>
  <img src="https://img.shields.io/badge/GitLab-FC6D26?logo=gitlab&logoColor=white" />
    <img src="https://img.shields.io/badge/GitLabRunner-FC6D26?logo=gitlab&logoColor=white" />
  <img src="https://img.shields.io/badge/ArgoCD-EF7B4D?logo=argocd&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20ECR-FF9900?logo=amazonelasticcontainerregistry&logoColor=white" />
</p>
<p>
  <img src="https://img.shields.io/badge/SPIRE-A6C444?logo=spiffe&logoColor=white" />
  <img src="https://img.shields.io/badge/Falco-00A5E6?logo=falco&logoColor=white" />
  <img src="https://img.shields.io/badge/SonarQube-4E9BCD?logo=sonarqube&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS%20WAF-FF9900?logo=awswaf&logoColor=white" />
  <img src="https://img.shields.io/badge/NIST-000000?logo=nist&logoColor=white" />
</p>
<p>
  <img src="https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white" />
  <img src="https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenSearch-005EB8?logo=opensearch&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20Athena-7D4099?logo=amazonathena&logoColor=white" />
</p>

<hr>

<h3 align="center">CJ OliveNetworks Cloud Wave 6기 | 팀 `최강zl존`</h3>

| [<img src="https://github.com/DongilMin.png" width="100">](https://github.com/DongilMin) | [<img src="https://github.com/gyuseon25.png" width="100">](https://github.com/gyuseon25) | [<img src="https://github.com/isuking6511.png" width="100">](https://github.com/isuking6511) | [<img src="https://github.com/dfadsfa.png" width="100">](https://github.com/dfadsfa) | [<img src="https://github.com/sojung102.png" width="100">](https://github.com/sojung102) |
| :---: | :---: | :---: | :---: | :---: |
| **민동일** | **심규선** | **김지호** | **장욱재** | **박소정** |

<br>

<h2 align="center">🚀 프로젝트 목표</h2>

| 구분 | 목표 |
| :---: | :--- |
| **🔐 보안** | **Zero Trust 기반 다층 방어**: 내/외부 위협 실시간 탐지 및 100% 자동화 대응 |
| **⚡ 성능** | **대규모 트래픽 처리 및 무중단 DR**: '올영세일' 수준 트래픽 처리, 2분 내 재해 복구 |
| **💰 비용** | **FinOps 기반 비용 최적화**: 유휴 리소스 및 스토리지 비용 자동 관리 및 추적 |

<br>

<h2 align="center">🏗️ 아키텍처</h2>

> 💡 **아래 제목을 클릭하면 상세 아키텍처 다이어그램이 펼쳐집니다.**

<br>

<details>
<summary><strong>[Architecture Diagram] 📍 AWS Seoul Region (Production / Staging)</strong></summary>
<br>
<table border="0">
 <tr>
  <td align="center"><img src="https://github.com/user-attachments/assets/4116044f-862b-48aa-bac7-13a4b1975c0b" width="100%" /></td>
  <td align="center"><img src="https://github.com/user-attachments/assets/18b6b3bf-4d14-400b-80cc-8e5352d1e712" width="100%" /></td>
 </tr>
</table>
</details>

<br>

<details>
<summary><strong>[Architecture Diagram] 🇯🇵 AWS Tokyo Region (DR Site)</strong></summary>

<p align="center">
  <img src="https://github.com/user-attachments/assets/323898de-7179-4fde-b4a0-7fde79ba35f5" width="800" />
</p>
<br>

### ✅ 주요 구성 요소
<table border="0"><tr><td align="left">
<ul>
<li><strong>🛰️ 컨테이너 이미지 이중화</strong>: 주 리전(서울)의 <strong>ECR</strong> 이미지를 재해 복구 리전(도쿄)으로 자동 복제</li>
<li><strong>⚡ 워크로드 자동 배포</strong>: <strong>EventBridge</strong>로 이미지 복제를 감지, <strong>Lambda</strong>를 통해 DR 리전의 <strong>ECS</strong>에 최신 버전 자동 재배포</li>
<li><strong>🔄 신속한 트래픽 전환</strong>: 장애 시 <strong>Route 53 가중치</strong> 조정을 통해 <strong>Warm Standby</strong> 상태의 <strong>Fargate</strong>로 트래픽 즉시 전환</li>
<li><strong>🌍 데이터 실시간 동기화</strong>: <strong>DynamoDB Global Tables</strong>를 활용하여 서울↔도쿄 리전 간 데이터 양방향 실시간 복제</li>
<li><strong>🛡️ 데이터 손실 최소화</strong>: 자동 동기화 및 <strong>PITR(시점 복구)</strong> 기능을 통해 RPO(복구 목표 시점) 최소화</li>
</ul>
</td></tr></table>

<br>



</details>

<table border="0"><tr><td align="left">
<ul>
<li><strong>Hybrid Cloud</strong>: <code>On-Premise</code> (GitLab) + <code>AWS Cloud</code> (EKS) 연동</li>
<li><strong>Multi-AZ</strong>: <code>운영계(Seoul)</code> 다중 AZ 구성으로 고가용성 확보</li>
<li><strong>Disaster Recovery</strong>: <code>DR Site(Tokyo)</code> Warm Standby 구성 (2분 내 자동 전환)</li>
</ul>
</td></tr></table>

<br>

<h2 align="center">✨ 핵심 기능</h2>

<h3 align="center">🔐 보안 (Security)</h3>

> 💡 **아래 3개의 주제를 클릭하면 상세 구현 내용과 증명 자료(이미지)가 펼쳐집니다.**

<br>

<details>
<summary><strong>[구현 상세] 1. 원칙: "절대 신뢰하지 말고, 항상 검증하라"</strong></summary>
<br>
    
* **서비스 간 상호 인증**: MSA 환경 내 모든 서비스 통신에 **mTLS** 상호 인증 적용
    <p align="center">
      <img width="650" height="300" alt="TLS vs mTLS Communication" src="https://github.com/user-attachments/assets/cef71004-f042-469f-8170-5d9a2d2fbbb8" />
    </p>

* **mTLS 자동화**: 수동 관리의 한계 → **SPIRE** 도입으로 **워크로드 증명(Attestation)** 기반 인증서 발급/갱신 **100% 자동화**
    <p align="center">
      <img width="650" height="400" alt="SPIRE Architecture" src="https://github.com/user-attachments/assets/9066d6a4-4674-4074-a3d4-7337d745c2c0" />
    </p>

* **인증서 탈취 대응**: **60초 수명**의 초단기 인증서(SVID)를 **30초** 주기로 자동 갱신하여 탈취 피해 최소화
    <p align="center">
      <img width="650" height="300" alt="Short-Lived SVID Renewal Proof" src="https://github.com/user-attachments/assets/e127d6e8-d7ae-444a-9cc5-bae5b10797fe" />
    </p>
</details>

<details>
<summary><strong>[구현 상세] 2. 자동화된 외부 위협 대응</strong></summary>
<br>

* **테스트 시나리오**: 대규모 **Credential Stuffing** 공격 및 개인정보 유출 상황 모의
    <p align="center">
      <img width="650" height="300" alt="Simulated Data Breach Scenario" src="https://github.com/user-attachments/assets/a8d7f2c6-47a4-45dd-8f6a-0ec858e66e51" />
    </p>

* **대응 파이프라인**: **탐지 → 차단 → 시각화 → 알림 → 분석 → 리포팅** 전 과정 100% 자동화
    <p align="center">
      <img width="650" height="300" alt="Automated Threat Response Pipeline" src="https://github.com/user-attachments/assets/b21fe029-d27e-47c5-a3ed-87f287392acf" />
    </p>

* **실시간 대응**: **WAF** 자동 차단 → **OpenSearch** 실시간 시각화 → **Slack** 즉각 알림
    <p align="center">
      <img width="650" height="300" alt="Real-time Detection & Alerting Demo" src="https://github.com/user-attachments/assets/32254136-5039-4a6f-819c-e56f287a5e64" />
    </p>

* **분석 및 리포팅**: **WAF Log (S3)** → **Athena** 자동 쿼리 → **SES** 일일 보고서 발송
    <p align="center">
      <img width="650" height="300" alt="Automated Log Analysis & Reporting" src="https://github.com/user-attachments/assets/b6717032-9c6d-4d8d-8d33-fa9f08b03cbe" />
    </p>
</details>

<details>
<summary><strong>[구현 상세] 3. CI/CD 파이프라인 보안 (DevSecOps)</strong></summary>
<br>

* **정적 코드 분석**: `SonarQube`를 통한 소스 코드 레벨의 잠재적 보안 취약점 사전 탐지
    <p align="center">
      <img width="650" height="300" alt="SonarQube SAST" src="https://github.com/user-attachments/assets/75a51d55-d680-4b82-b2bb-e7f67bd3bd56" />
    </p>

* **민감 정보 스캐닝**: `Git` 커밋 내 민감 정보(API 키 등) 실시간 탐지, 자동 비활성화 및 경고
    <p align="center">
      <img width="650" height="300" alt="Secret Scanning & Alerting" src="https://github.com/user-attachments/assets/06b46a5b-798d-4369-b2be-7ee69d49fe3d" />
    </p>
</details>

<hr>

<h3 align="center">⚡ 성능 (Performance)</h3>

<table border="0"><tr><td align="left">
<ul>
<li><strong>유연한 리소스 확장</strong>: <code>Prometheus</code> → <code>HPA</code> → <code>Karpenter</code> 연동으로 트래픽에 따른 동적 오토스케일링</li>
<li><strong>안정적인 요청 처리</strong>: <code>Kafka</code> 메시지 큐를 통한 비동기 처리로 대규모 트래픽 병목 현상 해소</li>
<li><strong>응답 속도 향상</strong>: <code>VPC Endpoint</code>를 통한 AWS 내부망 통신으로 네트워크 지연 최소화</li>
<li><strong>비용 대비 성능 극대화</strong>: <code>AWS Graviton</code>(ARM) 프로세서 도입으로 컴퓨팅 효율 최적화</li>
</ul>
</td></tr></table>

<hr>

<h2 align="center">🔬 성능 검증: '올영세일' 시나리오 스트레스 테스트</h2>

> 💡 **아래 제목을 클릭하면 상세 테스트 과정 및 결과가 펼쳐집니다.**

<br>

<details>
<summary><strong>[Test Details] 시나리오 정의, 실시간 스케일링, 테스트 결과</strong></summary>
<br>

* **시나리오 정의**:
    * **기준**: 올리브영 공식 트래픽 5단계 모델 기반
    * **목표**: 최고 부하 단계인 **'(S) Special - 올영세일'** (평시 20배 이상) 트래픽을 안정적으로 처리

    <p align="center">
      <img width="650" height="300" alt="Traffic Level Scenario" src="https://github.com/user-attachments/assets/3cf9d698-9d68-42bf-9ef7-fcc1b7d77565" />
    </p>

* **실시간 스케일링 동작**:
    * **Pod 확장 (HPA)**: `Prometheus`로 수집된 CPU/Memory 임계값 초과 시 HPA가 Pod 수를 **4개에서 13개로 확장**
    * **Node 프로비저닝 (Karpenter)**: HPA에 의해 스케줄링 불가능한 Pod 발생 시 `Karpenter`가 신규 Node(7개→10개)를 **Just-in-Time 방식으로 즉시 프로비저닝**

    <p align="center">
      <img width="650" height="300" alt="Real-time Scaling Visualization" src="https://github.com/user-attachments/assets/be64eb3d-67c9-4313-a2b5-355df6f53814" />
    </p>

* **테스트 결과 (Grafana 대시보드)**:
    * **결과**: 트래픽 폭증에 성공적으로 대응 후, 트래픽 감소 시 Pod와 Node가 설정된 기준에 따라 안정적으로 축소됨을 확인
    * **Pod 수**: **4 → 13 → 4** (안정적 복귀)
    * **Node 수**: **7 → 10 → 8** (비용 최적화를 위한 점진적 축소)

    <p align="center">
      <img width="650" height="300" alt="Grafana Dashboard Results" src="https://github.com/user-attachments/assets/6dd70aae-8b88-481e-9981-8c9bf5053d62" />
    </p>
</details>

<hr>

<h3 align="center">💰 비용 (Cost)</h3>

<table border="0"><tr><td align="left">
<ul>
<li><strong>체계적인 비용 관리</strong>: 전 리소스 <strong>태깅(Tagging)</strong>을 통한 팀/서비스 단위 비용 추적 및 분석 (FinOps)</li>
<li><strong>스토리지 비용 절감</strong>: <strong>S3 Lifecycle Policy</strong> (<code>Standard → IA → Glacier</code>) 자동 이전 (44% 절감)</li>
<li><strong>유휴 리소스 관리</strong>: <strong>Lambda + EventBridge</strong>로 심야 시간 개발 환경 리소스 자동 축소/종료</li>
<li><strong>예산 초과 방지</strong>: <strong>AWS Budget</strong> 설정으로 지정된 비용 임계값 초과 시 자동 알림 발송</li>
</ul>
</td></tr></table>
<br>

<h2 align="center">🚀 CI/CD Pipeline with GitLab, GitLab Runner, and Argo CD</h2>
<h3 align="center">🔧 GitOps 기반 배포 자동화</h3>

> 💡 **아래 항목을 클릭하면 CI/CD 아키텍처 다이어그램, 파이프라인 설명, 기술 스택 및 환경 변수 설정을 확인할 수 있습니다.**

<details>
<summary><strong>[Architecture Diagram] 🏗️ CI/CD Pipeline</strong></summary>
<br>

### 📊 아키텍처 구성
<img width="843" height="622" alt="image" src="https://github.com/user-attachments/assets/20575bfa-68d8-4b7b-8ebf-d197ef8e871d" />
</details>

<details>
<summary><strong>⚙️ CI/CD 파이프라인 설명</strong></summary>


#### ✅ CI (Continuous Integration): 빌드 및 통합 자동화
<table border="0"><tr><td align="left">
<ul>
<li><strong>코드 형상 관리</strong>: 개발자가 VPN을 통해 <strong>사설 GitLab</strong>으로 코드를 Push하여 버전 관리</li>
<li><strong>CI 파이프라인 실행</strong>: <strong>GitLab Runner</strong>가 코드 변경을 감지하여 CI 파이프라인 자동 실행</li>
<li><strong>컨테이너 이미지 생성</strong>: <strong>Docker 이미지 빌드</strong> 및 버전 태깅 후 <strong>AWS ECR</strong> Private Registry에 Push</li>
<li><strong>품질/보안 검증</strong>: <strong>SonarQube</strong> 코드 정적 분석 및 보안 취약점 스캔 수행</li>
<li><strong>배포 준비 완료</strong>: 모든 단계를 통과한 최종 이미지를 <strong>ECR</strong>에 저장하여 배포 가능한 상태로 관리</li>
</ul>
</td></tr></table>

#### ✅ CD (Continuous Deployment): 배포 자동화
<table border="0"><tr><td align="left">
<ul>
<li><strong>Manifest 업데이트 자동화</strong>: CI 성공 시 <strong>GitLab Runner</strong>가 배포 Manifest(<code>deployment.yaml</code>)의 이미지 태그를 최신 버전으로 자동 업데이트</li>
<li><strong>GitOps 기반 배포</strong>: <strong>Argo CD</strong>가 Manifest Repo의 변경 사항을 감지하여 실시간으로 동기화</li>
<li><strong>운영 환경 자동 배포</strong>: 변경된 Manifest를 기반으로 <strong>운영(Production) EKS 클러스터</strong>에 무중단 자동 배포</li>
<li><strong>안정적인 배포 전략</strong>: <strong>Staging → Production</strong> 단계별 점진적 배포 및 배포 실패 시 롤백 지원</li>
</ul>
</td></tr></table> 

</details>

<details>
<summary><strong>🛠️ 사용된 주요 기술 스택</strong></summary>

| 구성 요소          | 설명 |
|-------------------|------|
| **GitLab**        | 코드 저장 및 CI 트리거 |
| **GitLab Runner** | Docker-in-Docker 기반 CI, GitOps 자동화 |
| **AWS ECR**       | Docker 이미지 저장소 |
| **Argo CD**       | GitOps 기반 쿠버네티스 CD 도구 |
| **EKS (운영계)**  | 서비스가 실제 배포되는 클러스터 |

</details>

---
<h2 align="center">📡 Observability & AIOps — Loki · Tempo · Fluent Bit · Headlamp · Bedrock</h2>

<table border="0"><tr><td align="left">

**목표**
- 전 네임스페이스 로그/트레이스 수집 → Grafana에서 실시간 탐색/대시보드/알림  
- 중요한 이벤트는 **Bedrock**이 요약해 **Slack/이메일**로 전파(원인·영향·조치)

**선정 이유**
- **Fluent Bit**: 경량·고성능 에이전트(DS), CRI 로그/쿠버네티스 메타 자동 태깅  
- **Loki**: 라벨만 인덱싱 → 저장비용↓, K8s 라벨 기반 탐색(LogQL) 최적  
- **Tempo**: 단순 구조 + 오브젝트 스토리지 백엔드로 장기 보관 비용↓, 샘플링 유연  
- **Headlamp**: 경량 K8s 웹 콘솔, NLB로 외부에서 빠르게 클러스터 관찰  
- **Bedrock**: 알림 소음↓, 실행 가능한 요약/다음 액션 자동 생성(AIOps)

</td></tr></table>

<details>
<summary><strong>🗺️ 아키텍처(요약)</strong></summary>
<br>

**데이터 경로**
- **Logs**: Node마다 **Fluent Bit(DS)** → **Loki** → **Grafana(Explore/대시보드/알림)**  
- **Traces**: 앱(OTel SDK/오토 인스트루먼트) → **Tempo** → **Grafana Tempo**  
- **AIOps**: Grafana 알림(Webhook) → **Lambda** → **Bedrock 요약** → **Slack/Email**  
- **운영 UI**: **Headlamp(NLB, internet-facing)** 로 클러스터 전체 조회

**관측 범위**
- 앱 서비스(product/order/user 등) / Kafka / Karpenter / Ingress / 시스템 컴포넌트
</details>

<details>
<summary><strong>⚙️ 운영 흐름(실시간 알림)</strong></summary>
<br>

1) Fluent Bit이 컨테이너 로그를 수집하고 네임스페이스/파드/컨테이너 라벨을 부착  
2) Loki에 적재 → Grafana 대시보드/Explore에서 조회  
3) 룰(에러율↑, CrashLoopBackOff, 5xx, Kafka timeout 등) 충족 시 알림 발송  
4) 알림 페이로드를 Lambda가 수신 → **Bedrock**에 요약 프롬프트 전달  
5) **한 줄 요약 + 원인/영향/다음 액션**을 Slack/메일로 송신  
6) 필요 시 Tempo에서 해당 요청의 **TraceID**로 딥다이브(서비스 간 왕복 지연/스팬 오류 확인)
</details>

<details>
<summary><strong>📊 대시보드 인사이트</strong></summary>
<br>

**서비스/파드별 에러 추이** 및 상위 에러 키워드  
**Kafka** 오류 패턴(timeout/rebalance/backoff/disconnect 등)  
**Karpenter/HPA** 이벤트(프로비저닝 실패, 드리프트, 노드 변동)  
**CrashLoopBackOff / OOMKilled** 발생 현황(네임스페이스·파드별)  
**요청 지연/오류 비율**, 네트워크·스토리지 계열 에러(Conn refused/timeout/ENOSPC 등)  
**Trace**의 스팬 지연 병목, 다운스트림 서비스 원인 상관 분석
 
</details>

<details>
<summary><strong>🧭 운영 가이드 & 체크</strong></summary>
<br>

**접속/노출**: Headlamp는 NLB **internet-facing**(퍼블릭 서브넷 태그/라우팅 확인)  
**수집 안정성**: Fluent Bit CrashLoop 시 대부분은 설정 오타/들여쓰기/라벨키 불일치  
**보이는 로그 없음**: 시간 범위/라벨 필터 과도 여부, Loki distributor 주소, 네임스페이스 제외 규칙 확인  
**알림 소음 제어**: 치명 이벤트(5xx 급증, CrashLoop, Kafka timeout) → 단계적 룰 확장  
**장기 보관(옵션)**: 실시간은 Loki, 장기 분석은 Kinesis→S3(with 파티셔닝)로 이원화 가능
</details>

<details>
<summary><strong>💰 비용 최적화 포인트</strong></summary>
<br>

**Loki/Tempo**: 라벨 인덱싱/오브젝트 스토리지 백엔드로 저장비 절감  
**샘플링**: Tempo는 서비스·엔드포인트 별 샘플 비율 차등(핫패스 높게, 콜드패스 낮게)  
**수명주기**: S3 Lifecycle(Std→IA→Glacier) + 보존기간 룰, 불필요 라벨 최소화  
**에이전트 단일화**: Promtail 제거, **Fluent Bit로 통합**
</details>

**기대 효과**
장애 **탐지→원인분석→조치 제안** 리드타임 단축(알림 자동 요약)  
로그/트레이스 **상관분석**으로 MTTR↓, 재발 방지 액션 명확화  
저장·운영 비용 절감 + 운영 단순화(에이전트/파이프라인 일원화)
<h2 align="center">🛠️ 기술 스택</h2>

---

| 구분 | 기술 |
| :--- | :--- |
| **Cloud & Infra** | `AWS` `EC2` `EKS` `RDS Aurora` `S3` `Route53` `Lambda` `VPC` `ECS` `Fargate` `EventBridge` |
| **Container** | `Docker` `Kubernetes` `Karpenter` `Helm` `HPA` |
| **Backend** | `Go` `Java (Spring Boot)` `DynamoDB`|
| **CI/CD & IaC** | `GitLab` `GitLabRunner` `ArgoCD` `Terraform` `Amazon ECR` |
| **Security** | `SPIRE (mTLS)` `Falco` `SonarQube` `AWS WAF` `Secret Scanner` `NIST ZTA` |
| **Monitoring** | `Prometheus` `Grafana` `Loki` `Tempo` `headlamp` `OpenSearch` `Slack` |
| **Message Queue** | `Kafka` |
| **Data Analysis** | `Amazon Athena` `Amazon SES`|

<br>

<h2 align="center">📊 핵심 성과</h2>

| 영역 | 성과 |
| :---: | :--- |
| **보안** | SSL Labs `B` → `A` 등급 달성 |
| **성능** | '올영세일' 부하 테스트 통과 (무중단 트래픽 처리) |
| **DR** | 재해 복구 전환 **2분 이내** 달성 (목표 60% 단축) |
| **비용** | 스토리지 비용 **44% 절감** (실제 환경 54% 기대) |

<br>

<h2 align="center">📂 레포지토리</h2>

<table border="0"><tr><td align="left">
<ul>
<li><strong>MSA (Go)</strong>: <code>product-service</code>, <code>order-service</code></li>
<li><strong>MSA (Java)</strong>: <code>user-service</code></li>
<li><strong>Infrastructure</strong>: <code>eks-cluster</code>, <code>aws-infra-terraform</code></li>
</ul>
</td></tr></table>

</div>
