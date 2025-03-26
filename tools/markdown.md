---
title: Markdown 문서 작성법
layout: home
parent: 문서 작성 도구 사용법
nav_order: 1
permalink: /tools/markdown/
---

# 마크다운 문법 설명

우리 수업에서는 과제 문서를 마크다운 문법으로 작성합니다. 다음에서 간단한 마크다운 문법을 설명합니다.

## 1. 제목 작성

제목을 만들려면 제목 텍스트 앞에 1~6개의 # 기호를 추가합니다. 사용하는 #의 수에 따라 제목의 계층 구조 수준과 글꼴 크기가 결정됩니다.

```markdown
# A first-level heading
## A second-level heading
### A third-level heading
```
# A first-level heading
## A second-level heading
### A third-level heading

## 2. 텍스트 스타일 지정

주석 필드 및 `.md` 파일에서 굵게, 기울임꼴 또는 취소선 텍스트로 강조를 나타낼 수 있습니다.

| 스타일 | 구문 | 단축키 | 예시 | 출력 |
| --- | --- | --- | --- | --- |
| 굵게 | `** **` 또는 `__ __` | Command+B(Mac) 또는 Ctrl+B(Windows/Linux) | `**This is bold text**` | **굵게 표시된 텍스트** |
| 이탤릭체 | `* *` 또는 `_ _` | Command+I(Mac) 또는 Ctrl+I(Windows/Linux) | `_This text is italicized_` | *기울임꼴로 표시된 텍스트* |
| 취소선 | `~~ ~~` | None | `~~This was mistaken text~~` | ~~실수하여 취소된 텍스트~~ |
| 굵게 및 중첩된 기울임꼴 | `** **` 및 `_ _` | None | `**This text is _extremely_ important**` | **_매우_ 중요한 텍스트** |
| 모든 굵게 및 기울임꼴 | `*** ***` | None | `***All this text is important***` | ***모든 텍스트가 중요*** |
| 아래 첨자 | `<sub> </sub>` | None | `This is a <sub>subscript</sub> text` | <sub>아래 첨자 텍스트입니다.</sub> |
| 위 첨자 | `<sup> </sup>` | None | `This is a <sup>superscript</sup> text` | <sup>위 첨자 텍스트입니다.</sup> |
| 밑줄 | `<ins> </ins>` | None | `This is an <ins>underlined</ins> text` | <ins>밑줄이 그어진 텍스트</ins> |

## 텍스트 인용

`>`를 사용하여 텍스트를 인용할 수 있습니다.

```markdown
Text that is not a quote

> Text that is a quote
```

따옴표 붙은 텍스트는 왼쪽에 세로선으로 들여쓰기되고 회색 형식으로 표시됩니다.

Text that is not a quote

> Text that is a quote


Note

대화를 볼 때 텍스트를 강조 표시한 다음 R을 입력하면 주석의 텍스트를 자동으로 인용할 수 있습니다. 을(를) 클릭하고 **회신 인용**을 클릭하면 전체 주석을 인용할 수 있습니다. 단축키에 대한 자세한 내용은 [단축키](https://docs.github.com/ko/get-started/accessibility/keyboard-shortcuts)을(를) 참조하세요.

## 목록

하나 이상의 텍스트 행 앞에 -, *, 또는 +을(를) 입력하여 순서가 지정되지 않은 목록을 만들 수 있습니다.

```
- George Washington
* John Adams
+ Thomas Jefferson
```

- George Washington
* John Adams
+ Thomas Jefferson

## 단락
텍스트 줄 사이에 빈 줄을 두어 새 단락을 만들 수 있습니다.

## 각주
이 대괄호 구문을 사용하여 콘텐츠에 각주를 추가할 수 있습니다.

```
Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].

[^1]: My reference.  
[^2]: To insert a line break in Markdown, use the `<br>` tag.<br>This is the second line.
```

Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].

[^1]: My reference.  
[^2]: To insert a line break in Markdown, use the `<br>` tag.<br>This is the second line.

각주가 다음과 같이 렌더링됩니다.
