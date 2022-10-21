# Deploy Static Website to S3

스토리북 배포 작업을 테스트 해보기 위해 만든 예제입니다. 정적 웹사이트를 S3를 이용하여 배포합니다.

## 요구 사항

- URL를 통해 접근할 수 있다.
- 비공개로 유지되어야 한다.
- 스토리북 업데이트가 용이해야 한다.

## 구현 방안

요구 사항을 충족하기 위한 방법은 다음과 같습니다. 이 프로젝트는 아래 항목 중 일부만 포함합니다.

- Route 53과 S3 정적 웹 호스팅을 이용한다.
- S3 Bucket의 public access를 막고 특정 IP 주소만 허용한다. SourceIp 또는 VpcSourceIp를 이용한다.
- Github Actions를 이용하여 특정 조건에 업데이트 진행한다.

## 실행

**Serverless Framework 설치**  
이를 이용하여 CloudFormation 템플릿을 만듭니다.

```bash
npm install -g serverless
```

**AWS CLI Profile 등록**

```bash
aws configure --profile <profile>
```

**Profile 목록 확인**

```bash
aws configure list-profiles
```

**S3 만들기**  
IAM 권한은 S3와 CloudFormation이 필요합니다.

```bash
serverless deploy --aws-profile <profile>
```

## Stack

- Serverless Framework
- Github Actions
