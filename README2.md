# **Just the Docs**에서 검색 기능을 잘 활용하는 방법

### 1. **Front Matter 설정 (Search Enabled)**
기본적으로 Just the Docs 테마는 [Lunr.js](https://lunrjs.com/) 기반의 클라이언트 사이드 검색 기능을 제공합니다. 검색이 제대로 작동하려면 각 페이지의 `front matter`에 검색을 활성화해야 합니다.

```yaml
---
layout: default
title: "페이지 제목"
nav_order: 1
search: true
---
```
🔹 `search: true`가 없으면 해당 페이지가 검색 결과에 나오지 않을 수 있습니다.

---

### 2. **페이지 메타데이터 추가**
Just the Docs는 `headings`, `title`, `content` 등을 기반으로 색인을 만듭니다. 검색 결과에서 원하는 페이지가 잘 나오도록 하려면 메타데이터를 최적화해야 합니다.

#### (1) **title 및 description 추가**
```yaml
---
title: "법철학 입문"
description: "법철학의 기본 개념과 주요 사상가들을 소개합니다."
search: true
---
```
🔹 `description` 필드를 활용하면 검색 시 보다 정확한 미리보기가 가능합니다.

---

## **🔹 정규식 수정 (VS Code Find & Replace)**

이제 YAML의 두 번째 `---`까지만 검색하고, 그 직전 줄이 공백이 아닌 경우에만 `search: true`를 추가하도록 정규식을 수정하겠습니다.

---

### **1️⃣ 수정된 정규식**
```
(---\n(?:title:\s*.+\n)(?:.*\n)*?)([^\n]+)\n(---)
```
### **2️⃣ 바꿀 내용**
```
$1$2\nsearch: true\n$3
```

---

## **🔹 정규식 설명**
1. `---\n` → YAML front matter의 시작 (`---`)
2. `(?:title:\s*.+\n)` → `title:`이 포함된 두 번째 줄
3. `(?:.*\n)*?` → YAML 내부 내용을 탐색 (lazy match)
4. `([^\n]+)\n` → **공백이 아닌 마지막 줄**을 캡처  
   - YAML 마지막 줄이 공백이 아닌 경우만 `search: true` 추가
5. `(---)` → YAML 종료 (`---`)

---

## **🔹 적용 방법 (VS Code)**
1. `Ctrl + Shift + H` (전체 프로젝트 검색 및 바꾸기) 실행
2. **"찾을 내용"** 입력:  
   ```
   (---\n(?:title:\s*.+\n)(?:.*\n)*?)([^\n]+)\n(---)
   ```
3. **"바꿀 내용"** 입력:  
   ```
   $1$2\nsearch: true\n$3
   ```
4. **정규식 (.*) 버튼 활성화**
5. `모든 바꾸기` 클릭

---

## **📌 예제**
### ✅ **수정 전**
```yaml
---
title: "법철학 개론"
author: "홍길동"
date: "2025-03-17"
tags: ["법철학", "윤리"]
---
내용 시작
```

### ✅ **수정 후**
```yaml
---
title: "법철학 개론"
author: "홍길동"
date: "2025-03-17"
tags: ["법철학", "윤리"]
search: true
---
내용 시작
```

### 🚫 **공백이 있을 경우 (변경되지 않음)**
```yaml
---
title: "법철학 개론"
author: "홍길동"
date: "2025-03-17"

---
내용 시작
```
🔹 YAML 종료 전 공백 줄이 있을 경우 `search: true`를 추가하지 않음

---

## **🚀 정리**
✅ YAML 종료(`---`) 직전에 공백이 없는 경우에만 `search: true` 삽입  
✅ 마크다운 내부의 다른 `---`에는 영향을 주지 않음  
✅ VS Code 정규식 검색으로 간편하게 적용 가능  

이제 안전하게 YAML 구조를 유지하면서 `search: true`를 추가할 수 있습니다! 🚀