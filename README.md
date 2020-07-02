# lol_win_prediction

재미삼아 해본 롤 승부예측 프로젝트

dataset : https://www.kaggle.com/bobbyscience/league-of-legends-diamond-ranked-games-10-min/

데이터 설명
이 데이터는 다이아몬드 상위권~마스터 티어의 랭크게임 약 1만 판에서 딱 10분일 때 기록된 데이터입니다
attributes --> 10분에 기록된 미니언, 골드, 킬, 데스 등
target class --> 블루팀 승리or패배(블루팀승리->레드팀패배, 블루팀패배->레드팀승리)

칼럼 설명
blueWins : 블루팀 승리 여부(target class)

blueWard : 블루팀이 설치한 와드 갯수
blueWardDestroyed : 블루팀와드가 파괴된 횟수
blueFirstBlood : 블루팀이 퍼스트블러드를 기록
blueKills : 블루팀이 총 거둔 킬 수
blueDeaths : 블루팀 총 데스 수
blueAssists : 블루팀 총 어시스트 수
blueEliteMonsters : 에픽몬스터(용, 전령) 잡은 횟수
blueDragons : 블루팀이 잡은 드래곤 수
blueHeralds : 블루팀이 잡은 협곡의 전령 수
blueTowersDestroyed : 블루팀의 파괴된 타워 수
blueTotalGold : 블루팀의 총 얻은 골드
blueAvgLevel : 블루팀 레벨 평균
blueTotalExperiance : 블루팀이 획득한 총 경험치
blueTotalMinonsKilled : 블루팀이 처치한 미니언 수
blueTotalJungleMinonsKilled : 블루팀이 처치한 정글 몹 수
blueGoldDiff : 블루팀 기준, 레드팀과의 골드 차이
blueExperianceDiff : 블루팀 기준, 레드팀과 경험치 차이
blueCSPerMin : 블루팀 분 당 미니언
blueGoldPerMin : 블루팀 분 당 획득골드

타겟 클래스인 blueWins를 제외한 나머지 칼럼이
레드팀의 경우도 존재합니다. (ex:redWard, readWardDestroyed etc...)

블루팀의 승리와 correlation이 높은 칼럼들을 추출하고, 중복이나 반복되는 자료를 제거(data cleaning)한 후
데이터 정규화(normalization)하고 PCA를 이용하여 2차원을 축소해서 실험 가능성 확인-->PCA을 2d로 뿌려보니까 원에서 반반 나눈 형태로 거의 뭉쳐있더라.. 정확한 예측 어려울듯
아주 심플한 DNN 모델을 정의하고 학습하였습니다.
해보니까 학습은 굳이 DNN안쓰고 ML쪽 툴킷 써도 상관 없어보임

원체 역전도 자주나오고 변수도 많은 게임이라그런가 테스트셋 예측정확도가 72~4%에 머뭄
다른사람들 한것도 보니까 거의 이정도에 머물고 있었음

종강하고 심심풀이로 했는데 재밌었당

# Requirements
torch
seaborn
numpy
matplotlib
pandas
scikit-learn
