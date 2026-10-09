# prompt-skills

상상을 장면으로 옮기는 프롬프트 스킬 모음.

## seeandrun

**머릿속 장면을 읽고, 움직이는 문장으로.**

Seedance 2.5의 작업 방식에 Runway의 카메라·동작 표현 원칙을 더한 영상 프롬프트 스킬입니다. 이야기를 바꾸지 않고, 인물의 행동과 카메라의 시선이 더 분명하게 전달되도록 다듬습니다.

### 설치

```bash
npx --yes skills@latest add \
  "https://github.com/pthwoojin2-droid/prompt-skills" \
  --skill seeandrun \
  --yes
```

Windows PowerShell에서는 한 줄로 실행하세요.

```powershell
npx --yes skills@latest add "https://github.com/pthwoojin2-droid/prompt-skills" --skill seeandrun --yes
```

Codex를 명시해서 설치하려면 `--agent codex`를, 사용자 전체 범위에 설치하려면 `--global`을 추가하세요. 기본 명령은 현재 프로젝트에 설치합니다. Node.js와 npm이 필요합니다.

설치 가능한 스킬만 확인하려면:

```bash
npx --yes skills@latest add "https://github.com/pthwoojin2-droid/prompt-skills" --list
```

### 사용

Codex에서 스킬을 호출하고 원문을 붙여 넣습니다.

```text
$seeandrun
이 장면을 Seedance 2.5용으로 다듬어줘.
민지가 준호에게 열쇠 하나를 건네며 “이제 네 차례야.”라고 말한다.
마지막에는 준호만 그 열쇠를 들고 있다. 카메라는 고정. 자막과 BGM은 없다.
```

이미지·영상·음성 참조가 있다면 번호와 역할도 적어 주세요. 예를 들어 `@Image1은 민지의 외형`, `@Video1은 카메라 이동만`처럼 전달하면 됩니다.

기본 결과는 바로 사용할 수 있는 프롬프트 하나입니다. 원문의 언어와 정확한 대사, 사건 순서, 소품의 이동, 결말을 보존합니다. 원본 영상의 부분 편집과 앞뒤 연장도 다룹니다. 창작 보완이나 전후 비교가 필요하면 함께 요청하세요.

### 담고 있는 원칙

- Seedance를 중심에 두고, Runway의 원칙으로 기존 연출을 구체화합니다.
- 인물의 움직임과 카메라의 움직임을 구분합니다.
- 참조 번호와 역할을 유지하며, 보지 못한 자료의 내용을 지어내지 않습니다.
- 편집에서는 지정한 범위 밖의 원본을 보존합니다.
- 사용자가 정한 시간 구간은 유지하고, 총 길이만으로 임의의 시간표를 만들지 않습니다.
- 카메라·조명·소리를 빈칸 채우듯 추가하지 않습니다.

이 스킬은 프롬프트를 작성합니다. 영상 생성과 유료 API 호출은 별도의 실행 요청이 필요합니다. 실제 결과는 모델과 입력 자료에 따라 달라집니다.

### 구성

```text
skills/seeandrun/
  SKILL.md
  agents/openai.yaml
  references/
    seedance-foundation.md
    runway-layer.md
    task-compatibility.md
```

### 출처와 라이선스

이 저장소의 지침은 직접 작성했습니다. BytePlus 공식 `sd25-pe` v0.1.1과 아래 공식 문서를 참고했으며, 공식 스킬 원문이나 회사의 문서 파일을 그대로 배포하지 않습니다. BytePlus 또는 Runway가 배포하거나 보증하는 통합 스킬은 아닙니다.

- [BytePlus Seedance 2.5 프롬프트 가이드](https://docs.byteplus.com/en/docs/modelark/seedance-2-5-prompt-guide?redirect=1)
- [BytePlus Seedance 2.5 튜토리얼](https://docs.byteplus.com/en/docs/modelark/seedance-2-5)
- [BytePlus 공식 스킬 배포 경로](https://arkdocs-en.tos-ap-southeast-1.volces.com/skills/)
- [Runway AI Video Prompting Guide](https://runway.com/resources/ai-video-prompting-guide)
- [Runway Text-to-Video Prompting Guide](https://help.runwayml.com/hc/en-us/articles/42460036199443-Text-to-Video-Prompting-Guide)
- [Runway Image-to-Video Prompting Guide](https://help.runwayml.com/hc/en-us/articles/48324313115155-Image-to-Video-Prompting-Guide)

직접 작성한 저장소 파일에는 [MIT License](LICENSE)를 적용합니다. 외부 문서와 상표의 권리는 각 소유자에게 있습니다. 자료 확인일: 2026-10-09.
