# All Backgrounds

![SPT](https://img.shields.io/badge/SPT-5.0.0-blue?style=flat-square)
![EFT](https://img.shields.io/badge/EFT-1.1.5.1.47510-lightgrey?style=flat-square)
![BepInEx](https://img.shields.io/badge/BepInEx-6.0.0--be.788-orange?style=flat-square)
![IL2CPP](https://img.shields.io/badge/Runtime-IL2CPP-purple?style=flat-square)
![.NET](https://img.shields.io/badge/.NET-6.0-512BD4?style=flat-square)
![License](https://img.shields.io/badge/License-Custom%20%2F%20SPT--only-red?style=flat-square)
![Status](https://img.shields.io/badge/Status-Working-brightgreen?style=flat-square)

Разблокирует все фоны главного меню в SPT 5.0. Просто установите мод, и они все станут доступны для выбора. Не нужно править профиль, начинать новую игру или лезть в конфиги.

## Что разблокируется

Категория кастомизации `EnvironmentUI` — фон позади вашего персонажа в главном меню. Мод читает категорию из актуальной базы данных, поэтому он выдает доступ ко всему, что там есть, включая фоны, добавленные другими модами.

В ванильном SPT 5.0 по умолчанию заблокированы следующие фоны:
- **The Unheard Edition**
- **Cyber**
- **Miami / Hotline Tarkov**
- **Ending: And Survived**
- **Ending: In The Darkness**
- **Ending: Didn't Escape From Yourself**
- **Ending: For Humanity**
- **Server Room** (Серверная, `SeasonalBDEnvironmentUiType`)

Этот мод гарантирует, что все они будут разблокированы для вашего профиля.

## Как это работает

`CustomizationController.GetCustomisationStorage` возвращает:
`clone(templateTable.CustomisationStorage) + profile.CustomisationUnlocks`

Мод добавляет недостающие фоны в общий список шаблонов на этапе `OnLoadOrder.PostLoad`.

Это значит:
- **Файлы сохранений никогда не записываются.** Существующие профили также получают доступ.
- **При удалении мода фоны снова блокируются.** В вашем профиле ничего не остается.

## Изменения в 1.0.2 (Порт на SPT 5.0)

- Мод портирован на SPT 5.0.0.
- **Клиентская часть удалена:** SPT 5.0 теперь включает фон "Server Room" нативно (`SeasonalBDEnvironmentUiType`). Старый BepInEx-плагин, препатчер и бандлы с ассетами больше не нужны.
- Теперь мод работает исключительно на стороне сервера и работает "из коробки".

## Установка

Распакуйте zip-архив в папку SPT. Внутри находится только:

    SPT_Runtime\user\mods\UnlockAllBackgrounds\

Никаких клиентских установок не требуется.

## 👏 Благодарности

*   **Оригинальные авторы мода**: MyButtHasARash
*   **Команда SPT**: за сам проект и поддержку моддинга.
*   **BepInEx / HarmonyX / Il2CppInterop** — за инфраструктуру, на которой всё держится.
*   **Сообществу SPT-модеров** — за то, что примеры вообще существуют.

## ✨ Автор:
zzzNIKOzzz

## Оригинальная идея:
[UnlockAllBackgrounds](https://sp-mod.com/mod/2978/unlockallbackgrounds) мод от [MyButtHasARash](https://sp-mod.com/user/51018/mybutthasarash) (версия для SPT 4.1.6 / Mono)

## Лицензия:
MIT — делай что хочешь, просто не забудь упомянуть автора.
