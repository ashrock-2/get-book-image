# Book Image Downloader

구글 북스 API를 사용하여 ISBN 또는 책 제목으로 책 표지 이미지를 다운로드하는 CLI 도구입니다.

## 설치

```bash
npm install
```

## 사용법

```bash
# ISBN으로 검색
npm run book -- -i 9788966262281

# 책 제목으로 검색
npm run book -- -t "클린 코드"

# 여러 ISBN 동시 검색
npm run book -- -i 9788966262281 9788966261956

# 저장 경로 지정
npm run book -- -i 9788966262281 -o ./images
```

## 파이프라인 입력 지원

```bash
# 파일에서 ISBN 목록 읽기
cat isbn_list.txt | npm run book

# 직접 입력
echo "9788966262281" | npm run book
```

## 주요 기능

- ISBN 또는 책 제목으로 검색 가능
- 여러 책 동시 검색 지원
- 파이프라인 입력 지원
- 고품질 이미지 우선 다운로드 (large > medium > small > thumbnail)
- 커스텀 출력 디렉토리 지정 가능

## 옵션

- `-i, --isbn`: ISBN 번호 (여러 개 가능)
- `-t, --titles`: 책 제목 (여러 개 가능)
- `-o, --output`: 이미지 저장 경로 (기본값: ./downloads)

## 주의사항

- ISBN은 10자리 또는 13자리 형식만 지원
- 이미지가 없는 경우 경고 메시지 출력 후 다음 항목 처리
- 출력 디렉토리가 없는 경우 자동 생성
