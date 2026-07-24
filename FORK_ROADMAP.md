# Fork roadmap (LuckyCoders / Immich)

Планы **этого форка**, отдельно от [upstream Immich roadmap](https://immich.app/roadmap).

Upstream сознательно **не** добавляет встроенный 2FA / passkeys (см. [discussion #8175](https://github.com/immich-app/immich/discussions/8175), [#3338](https://github.com/immich-app/immich/discussions/3338), [#15719](https://github.com/immich-app/immich/discussions/15719)) и предлагает OAuth/OIDC. Здесь фиксируем то, что хотим иметь **в форке** для своей инстанции.

## Auth / безопасность входа

| Статус | Фича | Описание |
|--------|------|----------|
| Planned | **TOTP (2FA)** | Опциональное подтверждение входа кодом из аутентификатора (Google Authenticator, Aegis, Bitwarden, …) |
| Planned | **Passkeys / WebAuthn** | Вход через ключ браузера / аппаратный ключ (KeyPass, YubiKey, Windows Hello, …) |

Цели:

- не полагаться только на пароль Immich для публично доступного инстанса;
- не обязательно поднимать полный IdP (Authentik / Authelia), если хочется лёгкий встроенный MFA;
- функции опциональные (выключены по умолчанию).

Связанный комментарий upstream: [immich#3338](https://github.com/immich-app/immich/discussions/3338#discussioncomment-17764669).

### Возможные этапы (черновик)

1. Server: модели TOTP secret / WebAuthn credentials, API enroll + verify при login.
2. Web: UI настройки в Account / Security + challenge на login.
3. Mobile: поддержка TOTP при password login; passkeys — по возможности платформы.
4. Docs: как включить, бэкап recovery codes.

## Другие идеи форка (бэклог)

| Статус | Фича | Заметки |
|--------|------|---------|
| In progress / partial | Null `bucket_date` + personal APK | Photos tab crash fix; сборка через Actions |
| Upstream PR | Widget / asset deep-link L/R | [immich#30156](https://github.com/immich-app/immich/pull/30156) |
| Proposed upstream | Screenshots collection + hide from timeline | Комментарий в [immich#14449](https://github.com/immich-app/immich/discussions/14449) |
| Proposed upstream | Mobile: Merge people UI | [immich#30154](https://github.com/immich-app/immich/discussions/30154) |
| Later | Mobile merge people implementation | API уже есть; UI в приложении |

## Вне скоупа этого файла

Граф «кто с кем чаще на фото» — личный эксперимент, не цель Immich-форка.
