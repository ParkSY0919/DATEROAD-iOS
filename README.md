# DATEROAD (iOS 15.0+) 💘

> 쉽고 빠른 데이트로 가는 지름길 👩‍❤️‍👨
>
> - 현재 README는 psy가 개발한 내용을 중점으로 작성돼있습니다.
> - 데이트로드의 전체 README 내용은 [참조](https://github.com/TeamDATEROAD/DATEROAD-iOS)에서 확인 부탁드립니다.

![50](https://github.com/user-attachments/assets/2234b5a3-c447-4761-a7ff-16e8608c5545)

<br>

## 🩷 소개

> 서비스 소개
>
> - 커플들이 직접 공유하는 ‘장소 중심’이 아닌 ‘코스 중심’ 데이트 코스 공유 서비스
>
> 개발 인원
>
> - 14인 프로젝트 | 기획(2) · 디자인(2) · 서버(3) · iOS(4) · AOS(3)
>
> 개발 기간
>
> - 집중 기간: 2024.06 - 2024.07 (4주, iOS 4인)
> - 유지보수 기간: 2024.12 - 현재 (진행 중, iOS 3인)

<br>

## 🩷 About Developers

| [윤희슬](https://github.com/seuriseuljjeok)                                                              | [박신영](https://github.com/ParkSY0919)                                                                  | [김민서](https://github.com/kms0233)                                                                     | [이수민](https://github.com/cirtuare)                                                                    |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| <img src="https://github.com/user-attachments/assets/db4de1ef-d419-47cf-8561-eeb22fe88c1d" width="250"/> | <img src="https://github.com/user-attachments/assets/6e6aa930-c78f-4de7-966d-972b799123a0" width="250"/> | <img src="https://github.com/user-attachments/assets/341e8a75-fcd6-4203-9d38-68e2881fe3fd" width="250"/> | <img src="https://github.com/user-attachments/assets/c70a168b-32b7-4cbe-9456-3f2e7400c071" width="250"/> |
| <p align="center">`온보딩/로그인`<br>`메인 화면 & 마이페이지`</p>                                        | <p align="center">`코스 등록/불러오기`<br>`일정 등록/불러오기`</p>                                       | <p align="center">`코스 상세`<br>`코스 둘러보기 & 하단 탭바`</p>                                         | <p align="center">`데이트 일정`<br>`포인트 내역 & 내가 열람한 코스`</p>                                  |

<br>

## 🩷 주요 기능

> 💡 협업 프로젝트의 담당 기능은 **Bold** 및 ✅ 표시하였습니다.
>
> - 소셜로그인 기능 (애플, 카카오)
> - **코스 등록 및 불러오기 ✅**
> - **일정 등록 및 불러오기 ✅**
> - 코스 목록 조회 (지역, 가격 필터링)
> - 카카오톡 공유 기능 (데이트 일정)
> - 프로필 관리 기능
> - 포인트 시스템 (코스 등록 및 열람으로 포인트 획득/사용 등)

#### 1️⃣ 코스 등록하기 및 열람

| ![Instagram_post_-_4](https://github.com/user-attachments/assets/6232fd24-f906-49a8-9ea0-16d296545931) | ![Instagram_post_-_5](https://github.com/user-attachments/assets/0d648884-0d06-4043-9d31-03df52d434b9) |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |

- 내가 한 데이트 코스를 등록하고 포인트를 획득할 수 있습니다.
- 다른 커플들이 한 데이트를 포인트를 사용해 열람할 수 있습니다.
- 코스 상세 페이지에서 ‘내 일정에 추가하기’ 버튼을 눌러 내 데이트 일정으로 불러올 수 있습니다.

#### 2️⃣ 일정 등록하기 및 열람

| ![Instagram_post_-_10](https://github.com/user-attachments/assets/8e3a627f-e567-4ad5-ac11-63e560a09b67) | ![Instagram_post_-_6](https://github.com/user-attachments/assets/e9accf21-1c6c-4fb5-9ad8-f834ab5750fa) |
| ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |

- 내 데이트 일정을 등록할 수 있습니다.
- 내 데이트 일정을 확인할 수 있습니다.
- 지난 데이트는 코스 등록하기로 연동해 등록하고 포인트를 받을 수 있습니다.
- 카카오톡 공유하기를 통해 데이트 일정을 연인에게 공유할 수 있습니다.

<br>

## 🩷 기술 스택 및 내용

> Framework: `UIKit`, `AuthenticationServices`
>
> Architecture: `MVVM`
>
> Design Patterns: `API Router`, `DI/DIP`, `Facade`, `POP`, `Repository`, `Singleton`
>
> Reactive Programming: `Custom Observable Pattern`
>
> Library: `Moya`, `Amplitude-Swift`, `KakaoSDK`, `Kingfisher`, `Lottie`, `SnapKit`, `Then` ..

- 데이트 코스 및 일정 추가 기능에서 사용자 입력 데이터(코스명, 방문 장소, 소요시간 등)의 변화를 실시간으로 감지하고 UI를 자동으로 업데이트하는 반응형 시스템을 구현했습니다. 특히 AddCourseViewModel과 AddScheduleViewModel에서 입력값 검증과 실시간 UI 상태 관리에 효과적이었습니다.
- Moya와 API Router를 활용해 Endpoint를 명확히 정의하고, BaseService 상속 구조를 통해 공통 네트워크 로직을 재사용했습니다. 이를 통해 토큰 갱신과 에러 처리를 일관되게 구현하여 안정성을 확보했습니다.
- Facade Pattern과 Repository Pattern을 활용해 비즈니스 로직 및 데이터 접근 로직을 명확히 분리하여 코드 유지보수성을 향상시켰습니다.
- Serviceable, TimeRequireProtocol 등의 프로토콜을 활용해 공통 요소를 추상화하고, 새로운 기능 추가 시 코드 재사용성을 높였습니다.
- API 통신이 필요한 기능에서 토큰 만료 시 자동 갱신 메커니즘을 구현하여 사용자 경험 단절 없이 서비스 이용이 가능하도록 했습니다.
- CustomObservable의 lazyBind를 통해 데이터 집약적 작업이 발생하는 일정 등록 및 불러오기 화면에서 불필요한 UI 업데이트를 방지하고 성능을 개선했습니다.
- PHPickerViewController로 데이트 코스 등록 시 다중 이미지 선택과 대표 썸네일 지정 기능을 구현했습니다. 선택된 썸네일은 시각적으로 구분되도록 UI를 설계했으며, 모든 이미지는 JPEG 압축을 통해 업로드 효율성을 최적화했습니다.
- UICollectionViewDragDelegate와 DropDelegate를 이용해 데이트 코스 순서를 직관적으로 재배치할 수 있는 드래그 앤 드롭 기능을 구현했습니다. 드래그 시 둥근 모서리와 투명 배경으로 시각적 피드백을 제공하고, 드롭 완료 시 데이터 소스와 UI가 즉시 동기화되도록 처리했습니다. 추가로 편집 모드를 통해 아이템 삭제와 이동을 더욱 편리하게 만들었습니다.
