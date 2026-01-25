# CPU Scheduling Simulator (C)

운영체제(OS)의 핵심 원리인 **CPU 스케줄링 알고리즘**을 C 언어로 구현한 시뮬레이터입니다. 단순한 계산을 넘어 실제 운영체제 환경과 유사하게 **I/O 버스트(입출력 대기)** 상황을 포함하여 설계되었습니다.

---

## 프로젝트 개요

이 프로젝트는 다양한 스케줄링 알고리즘이 프로세스를 처리하는 방식과 그 효율성을 비교 분석하기 위해 제작되었습니다. 프로세스는 실행 중에 무작위로 I/O 요청을 보낼 수 있으며, 대기 큐(Waiting Queue)에서 I/O 작업을 마친 후 다시 준비 큐(Ready Queue)로 돌아오는 전체 사이클을 시뮬레이션합니다.

---

## 주요 기능

* **프로세스 생성 모드**
    * **Automatic Generation**: 설정된 범위 내에서 무작위로 도착 시간, 버스트 시간, 우선순위, I/O 정보를 생성합니다.
    * **Manual Creation**: 사용자가 직접 프로세스 상세 파라미터를 입력하여 특정 시나리오를 테스트할 수 있습니다.
* **I/O 버스트 시뮬레이션**: 프로세스 실행 중 특정 시점에 I/O 작업을 수행하며, 이때 CPU는 대기 중인 다른 프로세스에게 양보됩니다.
* **성능 분석 및 시각화**
    * **Gantt Chart**: 초 단위로 CPU의 프로세스 점유 상태를 시각적으로 출력합니다.
    * **Evaluation**: 프로세스별 대기 시간(Waiting Time), 반환 시간(Turnaround Time) 및 전체 평균 값을 계산합니다.

---

## 구현된 스케줄링 알고리즘

총 6가지의 주요 스케줄링 기법을 지원합니다.

1. **FCFS (First-Come, First-Served)**: 도착 순서대로 처리 (비선점)
2. **Non-preemptive SJF**: 실행 시간이 짧은 작업 우선 (비선점)
3. **Non-preemptive Priority**: 우선순위가 높은 작업 우선 (비선점)
4. **Round Robin (RR)**: 타임 퀀텀(Time Quantum) 기반 순환 (선점)
5. **Preemptive SJF (SRTF)**: 남은 시간이 가장 짧은 작업 우선 (선점)
6. **Preemptive Priority**: 도착 시점 기준 가장 높은 우선순위 작업 우선 (선점)

---

## 시작하기

### 컴파일 (GCC)
```bash
gcc -o scheduler cpu_scheduling.c
