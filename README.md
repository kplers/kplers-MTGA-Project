# MTGA_KO Project

매직 더 개더링 아레나와 관련된 여러 가지 프로젝트의 모음입니다.

현재는 아직 구상 단계에 있습니다.

## 1. 카드 텍스트 자동 번역 (Automatic Translation of Card Texts)

현재 나무위키 문서 작성의 자동화는 어느 정도 완성되어 있으나, 문제는 매직 더 개더링 아레나에 없는 카드의 경우, 한글 텍스트가 없거나, 현 오라클 텍스트와 맞지 않습니다. 

예시로, 최근 'enters the battlefield'가 'enters'로 변경되어, 한국어 텍스트도 '전장에 들어오다'가 '들어오다'로 간소화되었지만, 아레나에 없는 한글 카드 텍스트는 이러한 변화가 적용되어 있지 않습니다.

이에 따라 나무위키 문서를 작성할 때 아레나에 없는 카드들은 일단 영어 텍스트로 작성해 두고 나중에 직접 한글로 번역해 주어야 하는 불편함이 있습니다.

이 프로젝트의 목표는, 이 불편함을 해소하기 위해 아레나에 있는 텍스트 번역을 학습시켜 기존 카드의 영어 오라클 텍스트에 적용, 한국어 텍스트를 자동으로 얻는 것입니다. 일반 번역기를 이용하기 어려운 이유는, 아레나의 한글 번역에는 직역이 아닌 부분이 많기 때문입니다. (대표적인 것이 Target 텍스트) 

매직 더 개더링 텍스트에 특화된 번역기를 만들고, 이를 모든 카드에 적용하는 것이 목표입니다.

## 2. 나무위키 문서 자동화

위에서 언급했듯 나무위키 문서 자동화는 어느 정도 완성되어 있지만, 아직은 여러 문제점이 있습니다.

- 양면 카드가 지원되지 않음
- 코드가 매우 지저분함
- 오래 걸림

시간이 오래 소요되는 것은 대부분 카드의 세트 정보와 사용 가능 포맷 정보를 scryfall에서 일일이 불러오기 때문입니다. (사용 가능 포맷 정보는 카드 오브젝트에서 직접 가져올 수 있지만, 특히 세트 정보의 경우 오브젝트에 정보가 없어 직접 scryfall에서 그 카드 이름으로 검색하여 각 오브젝트의 세트 정보를 가져와야 해 비용이 큰 상태입니다.)

이러한 문제점을 해결하기 위해서 scryfall의 벌크 데이터를 이용해 카드 SQL 데이터베이스를 구축하여 이 데이터베이스로부터 문서를 작성하는 방안을 구상하였고, 데이터베이스 자체는 만들었습니다. 

그러나, 우선 데이터베이스를 업데이트하는데 15분 이상의 시간이 소요되는 것을 확인하였고, 아직 문서 작성 코드는 scrython 기반으로 되어 있어 데이터베이스 기반 코드를 다시 작성해야 하는 상황입니다.

그런데 그 문서 작성 코드가 총 2000줄이 넘는 규모에 코드가 지저분해서, DB 기반으로 깔끔하고 발전된 코드를 새로 작성하는 데에는 적지 않은 시간이 소요될 것으로 보고 있습니다.

또한 1번 프로젝트로 자동 번역된 카드 텍스트를 어떻게 적용할 지도 고민해야 할 부분입니다.

## 3. 게임 플레이 인공지능

MTG 아레나의 게임 플레이 인공지능을 만드는 프로젝트입니다. 이를 위해 사전 작업이 상당히 많이 필요할 것으로 예상되어, 1번/2번 프로젝트가 완성된 이후에 천천히 진행해 나갈 계획입니다.

## 4. 룰 엔진

cardforge 프로젝트와 비슷하지만 조금 더 발전된 UI의 룰 엔진을 만드는 프로젝트입니다. cardforge의 프로젝트 크기를 보시면 아시겠지만 매우 많은 시간과 노력이 필요한 프로젝트가 될 가능성이 높고, 시간이 나지 않으면 룰 엔진 프로젝트는 진행하지 않을 예정입니다.

## 5. K-Scryfall

1번 프로젝트를 바탕으로 번역된 한글 텍스트가 적용된, Scryfall과 비슷하지만 간소화된 형태의 웹사이트를 만드는 프로젝트입니다.

## 계획

가장 중요한 1번 프로젝트부터, 덜 바빠지는 내년 2월 이후부터 조금씩 만들어 볼 계획입니다.

## 메모

- 카드 데이터베이스 서버로 돌리기
- 최적화하기
- 더욱 자연스러운 번역
