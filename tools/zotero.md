---
title: Zotero 주석 작성하기
layout: home
parent: 문서 작성 도구 사용법
nav_order: 2
permalink: /tools/zotero/
---

# I. **Zotero 설치 및 사용법: 서지정보 등록 & Citekey 추출**

Zotero를 활용하여 **서지정보(참고문헌)를 관리**하고, **Citekey를 추출**하는 방법을 단계별로 설명하겠습니다.

---

## **1. Zotero 설치**
먼저 Zotero를 다운로드하고 설치해야 합니다.

### **🔹 Zotero 다운로드 및 설치**
1. [Zotero 공식 웹사이트](https://www.zotero.org/download/)에 접속합니다.
2. **"Zotero for Windows / macOS / Linux"** 버튼을 클릭하여 다운로드합니다.
3. 설치 파일을 실행하여 **Zotero를 설치**합니다.

✅ **플러그인 설치:**  
📌 **Better BibTeX for Zotero (BBT)**는 Citekey를 생성하는 필수 플러그인입니다.
- [Better BibTeX 다운로드](https://github.com/retorquere/zotero-better-bibtex/releases)  
- `.xpi` 파일을 다운로드한 후, Zotero에서 **Tools → Add-ons → Install Add-on From File**을 통해 설치합니다.

---

## **2. 서지정보 등록**
Zotero에서 참고문헌을 수집하는 방법은 여러 가지가 있습니다.

### **🔹 1) 직접 수동 입력**
1. Zotero 실행 → **"New Item" (새 항목 추가) 버튼 클릭**
2. 참고문헌의 유형 선택 (예: **Book, Journal Article, Thesis** 등)
3. **제목, 저자, 출판사, 발행 연도** 등 정보를 입력

### **🔹 2) DOI/ISBN 자동 입력**
1. **Zotero 상단 바코드(🔍) 아이콘 클릭**
2. **DOI 또는 ISBN 입력** → 자동으로 서지정보 불러오기

예제:
```
10.1093/mind/fzn050  (DOI 입력)
9780198250759  (ISBN 입력)
```

### **🔹 3) 웹페이지에서 자동 저장 (Zotero Connector 활용)**
1. **[Zotero Connector](https://www.zotero.org/download/connectors)** 브라우저 확장 프로그램 설치 (Chrome, Firefox 지원)
2. 논문 웹페이지(예: Google Scholar, JSTOR, PubMed)에서 **Zotero 아이콘 클릭** → 자동 저장

✅ **예제: Google Scholar에서 가져오기**
- [Google Scholar](https://scholar.google.com/)에서 논문 검색
- 논문 페이지에서 **Zotero 아이콘 클릭** → 저장

---

## **3. Citekey 추출 (Better BibTeX 사용)**
Zotero에서 **Better BibTeX(BBT) 플러그인**을 사용하여 Citekey를 생성하고 추출하는 방법입니다.

### **🔹 Citekey 확인 방법**
1. Zotero 실행
2. 참고문헌을 선택한 후 **우측 패널**에서 확인  
   - **"Better BibTeX Citation Key"** 항목이 표시됨  
   - 예: `scanlon2000`

### **🔹 Citekey 수정 방법**
1. 참고문헌을 선택 → **오른쪽 "Extra" 필드**에  
   ```
   citation key: scanlon2000
   ```
   입력하면 Citekey를 원하는 대로 변경 가능

---

## **4. Citekey 활용을 위한 BibTeX 파일 내보내기**
Citekey를 활용하려면 `.bib` 파일을 만들어야 합니다.

### **🔹 BibTeX 내보내기**
1. **Zotero에서 내보낼 참고문헌 선택**
2. **우클릭 → "Export Items" 클릭**
3. **"Better BibTeX" 형식 선택**
4. 파일 저장 (예: `my_references.bib`)

✅ 이 `.bib` 파일을 Markdown, LaTeX, Pandoc 등에서 사용할 수 있습니다.

---

## **5. (추가) Citekey 자동 생성 규칙 변경**
Citekey의 형식을 자동으로 지정하고 싶다면, **Better BibTeX 설정**에서 조정할 수 있습니다.

### **🔹 Citekey 규칙 변경 방법**
1. **Zotero > Preferences (설정) > Better BibTeX 탭으로 이동**
2. **"Citation Key Format"** 변경  
   - 기본값: `[auth][year]`
   - 예시:  
     ```
     [auth][year]
     ```
     → `scanlon2000`  
     ```
     [auth:lower]_[shorttitle]_[year]
     ```
     → `scanlon_contractualism_2000`

✅ 이렇게 설정하면 Citekey가 논문 제목이나 저자 이름을 포함하도록 조정할 수 있습니다.

---

## **6. 결론**
- **Zotero 설치 및 Better BibTeX 추가**
- **참고문헌 자동/수동 추가**
- **Citekey 확인 및 내보내기**
- **BibTeX 파일 저장 후 활용**

이제 Markdown, LaTeX, Pandoc 등에서 **Citekey 기반의 참고문헌 관리**를 효율적으로 할 수 있습니다! 🚀

---

# II. Zotero의 **Citekey**를 활용하여 **Markdown 문서에서 주석을 작성**하고, 이를 **Word 등 제출 문서 형식으로 변환**하는 일반적인 방법  

---

## 1. 필요한 도구 및 설정
Markdown 문서에서 Zotero Citekey를 사용하려면 **Pandoc**과 **Zotero Better BibTeX(BBT)** 플러그인을 함께 사용해야 합니다.  
아래 도구를 준비하세요.

### ✅ 필수 도구
1. **[Zotero](https://www.zotero.org/)** + [Better BibTeX for Zotero(BBT)](https://retorque.re/zotero-better-bibtex/)
2. **Pandoc** ([설치 링크](https://pandoc.org/installing.html))
3. **VS Code** ([설치 링크](https://code.visualstudio.com/))
4. **Pandoc Citation 스타일(.csl)** ([CSL 스타일 찾기](https://www.zotero.org/styles))

---

## 2. Zotero에서 Citekey 추출 (Better BibTeX 사용)
1. **Zotero에서 "Better BibTeX" 플러그인 설치**  
   - Zotero > **Tools** > **Add-ons** > "Better BibTeX" 설치
2. **BibTeX format으로 내보내기**  
   - Zotero에서 원하는 문헌을 선택한 후  
     - `Export Library` 또는 `Export Collection` 선택  
     - "Better BibTeX" 형식 선택  
     - `.bib` 파일을 저장 (예: `my_references.bib`)
3. **Citekey 확인**  
   - 항목을 선택한 후 **"Better BibTeX Citation Key"** 필드 확인  
   - 예: `@scanlon2000`

---

## 3. Markdown 문서에서 Citekey로 주석 작성하기
Markdown 문서에서 **Pandoc Citations Syntax**를 사용하여 주석을 작성할 수 있습니다.  
형식:
```markdown
이것은 Scanlon의 논의이다 [@scanlon2000, p. 45].
```
예제:
```markdown
# 법철학과 사회정의

법철학에서 인간 존엄성 개념은 다양한 방식으로 논의된다. 예를 들어, Scanlon(2000)은 특정한 기준을 제시하였다 [@scanlon2000, p. 45].

## 참고문헌
```

---

## 4. Markdown 문서를 Word로 변환하기 (Pandoc 사용)
Markdown 파일(`document.md`)을 **.docx, .pdf 등으로 변환**하려면, 아래 명령어를 사용하면 됩니다.

### 🔹 기본 변환 명령어
```bash
pandoc document.md --citeproc --bibliography=my_references.bib -o output.docx
```
🔹 **옵션 설명**  
- `--citeproc`: Zotero BibTeX Citekey를 참고문헌 처리  
- `--bibliography=my_references.bib`: BibTeX 파일 지정  
- `-o output.docx`: Word 문서로 변환  

### 🔹 CSL 스타일 적용 (예: Chicago, APA 등)
원하는 스타일을 적용하려면 `.csl` 파일을 다운로드한 후 적용할 수 있습니다.
```bash
pandoc document.md --citeproc --bibliography=my_references.bib --csl=chicago.csl -o output.docx
```

📌 [CSL 스타일 다운로드](https://www.zotero.org/styles)에서 원하는 스타일을 찾을 수 있습니다.

---

## 5. VS Code에서 Markdown & Pandoc 활용하기
1. **Markdown 파일 작성 (`.md` 확장자)**
2. **Pandoc 실행**  
   - VS Code **터미널**(`Ctrl + ~`)에서 `pandoc` 명령어 실행
3. **Word 변환된 파일 확인 (`.docx`)**
4. **Zotero 내장 인용 기능 활용하여 수정 가능**

---

## 🔥 결론
- **Markdown 문서에 Zotero Citekey 사용** → `[@scanlon2000]`
- **Pandoc으로 .md → Word 변환** (`.bib` 활용)
- **CSL 스타일 적용 가능** (APA, Chicago 등)

이 방법을 활용하면 **학술 논문 작성 및 문헌 관리**를 효율적으로 할 수 있습니다! 🚀
