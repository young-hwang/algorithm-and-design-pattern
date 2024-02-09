# Bellman Ford Algorithm

최단 거리를 구하는 알고리즘

|              기능               |                       특징                        | 시간 복잡도(노드: V, 에지: E) |
|:-----------------------------:|:-----------------------------------------------:|:--------------------:|
| 특정 출발 노드에서 다른 모든 노드 까지의 최단 경로 | 음수 가중치 에지가 있어도 수행 가능, 전체 그래프에서 음수 사이클의 존재 여부 판단 |        O(VE)         |

# 핵심 이론

3가지 단계의 원리로 동작

## 1. 에지 리스트로 그래프 구현하고 최단 경로 리스트 초기화

에지를 중심으로 동작하므로 에지 리스트를 구현

최단 경로 리스트를 출발 노드는 0, 나머지 노드는 무한대로 초기화

## 2. 최단 경로 리스트 업데이트

최단 경로 리스트를 업데이트 반복 횟수는 노드 개수 - 1
모든 에지를 순회하며 최단 경로 리스트를 업데이트

## 3. 음수 사이클 존재 여부 판단

모든 에지를 한 번씩 다시 사용해 업데이트 되는 노드가 있는지 확인
업데이트 되는 노드가 있다면 음수 사이클이 있다는 의미이고 2단계에서 도출된 정답 리스트가 무의미함
최단 거리를 찾을 수 없는 그래프