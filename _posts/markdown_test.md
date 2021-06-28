---
layout: single
title:  "sol upload test"
---

## solidity test
**마크다운 문법테스트**
---
`투표장 생성 부분`

```solidity
pragma solidity >=0.4.22 <0.7.0;


contract BVC {

    struct Voter {
        uint phone;
        uint votedPlace;
    }

    struct Candidate {
        uint candidateID;
        uint placeID;
        uint voteCount;
    }

    struct PollingPlace {
        uint placeID;
        bool isStarted;
    }

    Voter[] public voterList;
    Candidate[] public candidateList;
    PollingPlace[] public placeList;

    //-- 투표장 구조체 생성. set 함수와 get 함수를 연달아 사용해야 투표장을 하나 생성하고 해당 투표장의 ID를 가져올 수 있음.
    function setPollingPlace() public {
        placeList.length += 1;
        uint extensionPlaceID = placeList.length - 1;
        placeList[extensionPlaceID].placeID = extensionPlaceID;
        placeList[extensionPlaceID].isStarted = false;
    }

    function getPollingPlace() public view returns(uint, bool){ // return으로 uint 형식의 방금 만든 투표장 번호를 줌
        return (placeList[placeList.length - 1].placeID, placeList[placeList.length - 1].isStarted);
    }
    //-- 투표장 구조체 생성
    ```
    
    ---
    'markdown으로 다이어그램'
    ```mermaid
    graph LR
      server-->appRouter
      server-->webRouter
      webRouter-->blockFunc
      webRouter-->dbFunc
      webRouter-->funcHandling   
    ```
    ---
    ~~오늘은 여기까지~~
    ---
