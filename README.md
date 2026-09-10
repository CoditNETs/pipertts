# Debian-пакет Piper TTS (`pipertts`)

Автономная, работающая оффлайн система синтеза речи (TTS), упакованная для дистрибутивов Linux на базе Debian/Devuan.
Все компоненты, библиотеки и голосовые модели изолированы внутри иерархии `/usr/local/`.

## Особенности

- **Включенный голос**: Русский (`ru_RU-irina-medium`)
- **Автономность**: Устанавливает исполняемые файлы, C++ библиотеки времени выполнения (`libonnxruntime`, `libpiper_phonemize`) и данные `espeak-ng-data` в `/usr/local/`
- **Скрипт-обертка**: Включает `/usr/local/bin/pipertts` для быстрого вывода речи в консоли через ALSA (`aplay`).

## Установка

Скачайте готовый `.deb` пакет со страницы [Releases](https://github.com/CoditNETs/pipertts/releases/tag/1.2.0-codit1) и установите его через `dpkg`:
```bash
dpkg -i pipertts_1.2.0_amd64.deb
```
Если в системе отсутствуют необходимые системные зависимости, разрешите их автоматическую установку:
```bash
apt install -f
```

## Использование

```bash
# Direct argument synthesis
pipertts "Привет! Проверка автономного синтеза речи."

# Pipe synthesis
echo "Сообщение из потока stdin" | pipertts
```
## Источники и благодарности

В данном пакете используются готовые скомпилированные бинарные файлы и библиотеки проекта **Piper TTS**:
- **Официальный репозиторий:** [github.com/rhasspy/piper](https://github.com/rhasspy/piper)
- **Релизы бинарников:** Бинарный файл `piper` и сопутствующие библиотеки (`libpiper_phonemize`, `libonnxruntime`, `espeak-ng-data`) загружены из официальных релизов [rhasspy/piper/releases](https://github.com/rhasspy/piper/releases).
- **Сборка пакета и обертка ALSA**: Поддержка и сборка — CoditNETs.

## Лицензия

Данная сборка пакета распространяется под лицензией MIT. Исходные компоненты сохраняют свои соответствующие открытые лицензии.
