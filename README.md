# 중앙 워크플로우 관리 리포지토리 (Central Workflows Repository)

이 리포지토리는 조직의 모든 GitHub Actions 워크플로우를 중앙에서 관리하고 유지보수하기 위한 공간입니다. 워크플로우의 재사용성을 높이고, 일관성을 유지하며, 관리를 용이하게 하는 것을 목표로 합니다.

## 🌟 왜 워크플로우를 중앙에서 관리해야 할까요?

- **재사용성**: 여러 리포지토리에서 공통으로 사용되는 워크플로우를 한 곳에서 관리하여 중복을 제거합니다.
- **일관성**: 모든 프로젝트에서 동일한 버전의 워크플로우를 사용하여 배포 및 테스트 프로세스의 일관성을 보장합니다.
- **관리 용이성**: 워크플로우의 변경이 필요할 때, 이 리포지토리만 수정하면 모든 관련 리포지토리에 변경 사항이 적용됩니다.
- **보안**: 워크플로우에 사용되는 시크릿 및 접근 권한을 중앙에서 관리하여 보안을 강화할 수 있습니다.

## 🚀 시작하기

이 리포지토리의 워크플로우를 사용하려면, 여러분의 프로젝트의 `.github/workflows` 디렉토리에서 다음과 같이 워크플로우를 호출할 수 있습니다.

```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    uses: <your-organization>/central-ops/.github/workflows/reusable-build.yml@main
    with:
      node-version: 18
    secrets:
      NPM_TOKEN: ${{ secrets.NPM_TOKEN }}
```

## 🤝 기여하기

워크플로우 추가 또는 수정에 대한 기여를 환영합니다! 기여하시려면 다음 단계를 따라주세요.

1. 이 리포지토리를 포크합니다.
2. 새로운 브랜치를 생성합니다 (`git checkout -b feature/add-new-workflow`).
3. 변경 사항을 커밋합니다 (`git commit -m 'Add a new reusable workflow for deployment'`).
4. 브랜치에 푸시합니다 (`git push origin feature/add-new-workflow`).
5. Pull Request를 생성합니다.

Pull Request는 검토 후 병합될 것입니다.

## 📞 문의

궁금한 점이 있다면 언제든지 이슈를 생성하여 문의해주세요.
