# 디지털 실적 입력 목업

원본 HTML을 변경 없이 `index.html`로 배치한 정적 사이트입니다.
Vue나 Node 패키지 설치 및 빌드는 필요하지 않습니다.

## 로컬 실행

```sh
python3 -m http.server 8080
```

브라우저에서 http://localhost:8080 을 엽니다.
폰트, 아이콘, 로고는 원본과 동일하게 외부 URL을 사용하므로 인터넷 연결이 필요합니다.

## GitHub Pages 배포

1. 사용할 GitHub 계정/조직에 빈 저장소를 생성합니다.
2. 아래 명령의 OWNER를 실제 계정/조직으로 바꾸고 실행합니다.

```sh
git remote add origin https://github.com/OWNER/hanwha-ecotec-production-result-demo.git
git push -u origin main
```

3. GitHub 저장소의 **Settings → Pages → Build and deployment → Source**를 **GitHub Actions**로 설정합니다.
4. **Actions → Deploy static site to Pages → Run workflow**에서 `main`을 실행합니다.
5. 성공 후 배포 작업의 `github-pages` 환경에서 실제 사이트 주소를 확인합니다.

기본 주소: `https://OWNER.github.io/hanwha-ecotec-production-result-demo/`
이후 `main`에 push할 때마다 자동으로 배포됩니다.
저장소 가시성과 계정 요금제는 GitHub Pages 사용 조건을 충족해야 합니다.

배포 설정은 기존 `hanwha-sf-pos/.github/workflows/deploy-pages.yml`을 참고했습니다.
단일 HTML만 배포하므로 Node 빌드 대신 `dist/index.html`에 복사합니다.
현재 원격 저장소 생성, push, 실제 Pages 배포는 수행하지 않았습니다.
