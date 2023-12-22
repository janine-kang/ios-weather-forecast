# 날씨 앱
---

### Table of Content

> ** 1️⃣ OverView**
>
> - 결과물
> - 프로젝트 참여자
> - 프로젝트 기간
>
> ** 2️⃣ 프로젝트 구현**
>
> - 프로젝트 설계
> - 사용 기술/구성
> - 태스크 매니지먼트
> - 프로젝트 파일 구조
> - 구현 기능
> - 구현 상세
>
> ** 3️⃣ 습득 지식**
>
> - Trouble Shooting
> - Keywords

## 1️⃣ OverView

### 📍 결과물

### 📍 프로젝트 참여자

<table>
<tr>
<th>🐰 Rarla</th>
<th>🐠 Janine</th>
</tr>
<tr>
<td>
<img src="https://avatars.githubusercontent.com/u/30936939?v=4" width="90" height="90">
<div>@rarla</div>
</td>
<td>
<img src="https://avatars.githubusercontent.com/u/76927263?v=4" width="90" height="90"> 
<div>@janine-kang</div>
</td>
</tr>
</table>

### 📍 프로젝트 기간

> 2023.11.20 ~ 2023.12.22 (5 weeks)

## 2️⃣ 프로젝트 구현

### 📍 프로젝트 설계

- 디자인 패턴: `MVC`

### 📍 사용 기술/구성

- Swift 기반 어플리케이션 작성
- UIKit framework
- Code Base UI

### 📍 태스크 매니지먼트

- Notion
- Discord

### 📍 프로젝트 파일 구조

```
WeatherManager App
├── Controllers
│   └── WeatherViewController.swift
├── Extensions
│   ├── Double.swift
│   ├── String.swift
│   ├── UIImageVIew.swift
│   ├── UILabel.swift
│   ├── UIStackView.swift
│   └── UIView.swift
├── Info.plist
├── Models
│   ├── DTOs
│   │   ├── Coordinate.swift
│   │   ├── CurrentWeather.swift
│   │   ├── FiveDayForecast.swift
│   │   ├── Main.swift
│   │   ├── SystemData.swift
│   │   └── Weathers.swift
│   ├── Services
│   │   └── IconService.swift
│   └── WeatherManager.swift
├── Network
│   ├── CacheManager.swift
│   ├── Constnats
│   │   ├── Endpoint.swift
│   │   ├── Environment.swift
│   │   ├── HttpMethod.swift
│   │   └── UrlString.swift
│   ├── NetworkManager.swift
│   ├── Request.swift
│   └── WeatherAPIProtocol.swift
├── Resources
│   ├── AppDelegate.swift
│   ├── Assets.xcassets
│   │   ├── AccentColor.colorset
│   │   │   └── Contents.json
│   │   ├── AppIcon.appiconset
│   │   │   └── Contents.json
│   │   ├── Contents.json
│   │   └── background.imageset
│   │       ├── Contents.json
│   │       └── background.png
│   ├── Base.lproj
│   │   └── LaunchScreen.storyboard
│   └── SceneDelegate.swift
├── Views
│   ├── CurrentWeatherCollectionReusableView.swift
│   ├── GraphView.swift
│   └── WeatherTimeViewCell.swift
└── env.xcconfig
```

### 📍 구현 기능

#### 메인 화면
<table>
<tr>
<th>구동 화면</th>
<th>구현 기능</th>
</tr>
<tr>
<td>
<img width="280" height="auto" alt="Screenshot1" src="https://github.com/janine-kang/ios-weather-forecast/assets/76927263/6604b850-323c-4690-bb04-82ff8c00c0b7">
</td>
<td>
  <li>진입 시 openweathermap API로 현재 날씨, 5일 예보 정보 가져오기</li>
  <li>CollectionView와 UICollectionViewCell 재사용을 활용하여 UI 표기</li>
</td>
</tr>
</table>

#### 위치 좌표 설정

<table>
<tr>
<th>구동 화면</th>
<th>구현 기능</th>
</tr>
<tr>
<td>
<img src="https://github.com/janine-kang/ios-weather-forecast/assets/76927263/0902a0f2-5aef-4e42-993e-2a1a81a18e6a" alt="Screenshot2"  width="280" height="auto" />
</td>
<td>
  <li>위치 설정 버튼 클릭 시 UIAlertController 활용하여 액션시트 표기 </li>
  <li>위도, 경도 입력 후 변경 버튼 클릭 시 API 재 요청 후 Collection View 데이터 업데이트</li>
</td>
</tr>
</table>


### 📍 구현 상세

- UICollection View를 활용한 UI 구현
- UICollectionViewFlowLayout 이용하여 레이아웃 설정
- Open Weather Map API의 데이터 형식을 고려한 모델 타입 구현
- BaseURL 은닉화 위해 .xcuserdata 파일 사용
- CoreLocation을 활용한 사용자의 위도, 경도, 주소 정보 가져오기
- URLSession을 활용한 Network 통신 구현
- 범용성과 재사용성, 유연성을 고려한 네트워킹 타입 구현
- UIRefreshControl을 활용한 Refresh 구현
- UIAlertController 내 textField 활용
- 날씨 아이콘 NSCache를 활용해 Cache 처리
- Observer 패턴 활용하여 통신 데이터와 VC 간 1:N 관계 구현

## 3️⃣ 습득 지식

<table>
<tr>
<th>🐰 Rarla</th>
<th>🐠 Janine</th>
</tr>
<tr>
<td>
<li>UICollection View, UICollectionHeaderView를 활용한 UI를 구현</li>
<li>CoreLocation을 활용한 위도, 경도, 주소</li>
<li>NSCache를 활용한 이미지 캐싱 처리</li>
<li>1:N관계에서는 Delegate 패턴보다 Observer 패턴이 더 적합</li>
</td>
<td>
<li>CoreLocation</li>
<li>Observer 패턴</li>
<li>URLSession</li>
<li>BaseURL 은닉화 방법(3가지)</li>
<li>AutoLayout
(<code>CHCR</code> / <code>Constraint</code> )</li>
</td>
</tr>
</table>
