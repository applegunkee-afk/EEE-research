# refs/ — 참고문헌 관리

Zotero 연동 전까지 참고문헌을 저장소 안에서 직접 관리합니다.

| 파일 | 역할 |
|---|---|
| `references.bib` | LaTeX/Overleaf 인용의 **원본**. `\bibliography{refs/references}`로 사용 |
| `references.md` | 사람이 읽는 색인 (주제 태그, 연관성 메모, 읽기 상태) |

## 1. 인용 키 규칙

`firstauthorYEARkeyword` — 모두 소문자, 공백·특수문자 없음

- `firstauthor`: 1저자 성(last name)
- `YEAR`: 출판 연도 4자리
- `keyword`: 제목의 핵심 단어 1개 (짧게)
- 충돌 시 끝에 `a`, `b` 추가 (예: `kim2024leoa`, `kim2024leob`)

## 2. 새 문헌 추가 절차

1. **실존 여부 검증**: DOI(doi.org) 또는 IEEE Xplore 등 출판사 페이지에서 확인. 검증되지 않은 문헌은 추가하지 않습니다.
2. **BibTeX 확보**: 출판사 페이지의 "Cite / Export BibTeX" 또는 `https://doi.org/<DOI>`에 `Accept: application/x-bibtex` 요청으로 받기.
3. **`references.bib`에 추가**: 키를 위 규칙으로 바꾸고, 해당 주제 섹션 아래에 붙여넣기.
4. **`references.md`에 한 줄 추가**: 같은 키, 태그, 연관성 한 줄, 상태(`todo`부터 시작).
5. 같은 커밋으로 두 파일을 함께 커밋.

## 3. 나중에 Zotero로 전환할 때

1. 이 `references.bib`를 Zotero에 Import (File → Import) 하여 기존 항목 이관.
2. Better BibTeX 플러그인 설치 후 인용 키 형식을 `auth.lower + year + shorttitle(1,1).lower`로 지정하면 현재 규칙과 거의 일치합니다.
3. 컬렉션을 "Keep updated" 옵션으로 `refs/references.bib`에 Export → 이후 이 파일은 Zotero가 자동 갱신 (직접 수정 금지).
4. `references.md`는 메모/읽기 상태용으로 계속 유지하거나, Zotero 태그·노트로 옮긴 뒤 삭제.
