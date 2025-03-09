## MONN 재구현

### 📌 프로젝트 개요
단백질-리간드 상호작용 예측을 위한 딥러닝 모델인 MONN을 재구현하고자 했습니다. 단백질을 CNN 기반 모듈로 각각의 정보를 처리한 후, 두 정보를 종합해 결합 친화도를 예측하는 방식으로 작동합니다RDKit을 활용한 화합물 데이터 처리, 그래프 기반 뉴럴 네트워크(GNN) 적용, 전처리 관련 코드가 포함되어 있습니다.

### 📂 주요 내용
특징 엔코딩 (Feature Encoding)

- 단백질 특징 (Protein Features)
  - CNN을 활용한 특징 추출
  - BLOSUM62 행렬을 이용한 residue 특성 인코딩 (20x20 matrix)
  - Residue 최대 개수를 고려하여 패딩 적용

-리간드 특징 (Ligand Features)
  - Graph Convolution 적용
  - 원자 특징 벡터 (atomwise feature): 길이 82
  - 원자 종류 (63), Degree (6), Explicit valence (6), Implicit valence (6), Aromatic (1) → 총 82개 요소
  - 결합 특징 벡터 (bondwise feature): 길이 6
  - 결합 종류 (4), Conjugate (1), Ring (1) → 총 6개 요소

### ✅ 결론
- RDKit을 활용한 리간드 분자 특성 처리
- CNN을 통한 단백질 특징 추출
- Graph convolution을 활용한 리간트 특징 추출
