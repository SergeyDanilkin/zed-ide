# zed-ide

#Plugins

- HTML
- SQL
- Git Firefly
- PHP
- SCSS & Sass
- XML
- LOG
- Emmet
- env
- Tailwind Syntax
- Blade
- JSON5
- HTML Snippets
- JavaScript Snippets
- PHP Snippets
- Laravel
- Catppuccin
- Catppuccin Icons
- Prisma #

Pint
composer global require laravel/pint
composer global config bin-dir --absolute  # путь к папке 
nano ~/.zshrc
export PATH="$HOME/.config/composer/vendor/bin:$PATH"  # в конец
source ~/.zshrc
nano ~/.bashrc
export PATH="$HOME/.config/composer/vendor/bin:$PATH"
source ~/.bashrc

# Settings
{
    "cli_default_open_behavior": "existing_window",
    "icon_theme": "Catppuccin Latte",
    "theme": "Catppuccin Latte - No Italics",

    "vim_mode": true,
    "relative_line_numbers": "enabled",
    "buffer_font_family": ".ZedMono",
    "buffer_font_size": 16,
    "ui_font_size": 15,
    "show_whitespaces": "all",
    "wrap_guides": [80, 100, 120],
    "preferred_line_length": 120,
    "soft_wrap": "none",
    "show_wrap_guides": true,

    "remove_trailing_whitespace_on_save": true,
    "ensure_final_newline_on_save": true,

    "tab_size": 4,
    "hard_tabs": false,

    "autosave": "on_focus_change",

    "format_on_save": "on",

    "cursor_blink": true,
    "cursor_shape": "bar",
    "scroll_beyond_last_line": "one_page",

    "scrollbar": {
        "show": "auto",
    },

    "toolbar": {
        "breadcrumbs": true,
    },

    "terminal": {
        "font_size": 14,
        "working_directory": "current_project_directory",
    },

    "project_panel": {
        "dock": "left",
    },

    "outline_panel": {
        "dock": "right",
    },

    "languages": {
        "PHP": {
            "language_servers": ["intelephense", "!phpactor"],
            "tab_size": 4,
            "format_on_save": "on",
            "formatter": {
                "external": {
                    "command": "./vendor/bin/pint",
                    "arguments": ["--quiet", "{buffer_path}"],
                },
            },
        },

        "Blade": {
            "tab_size": 4,
            "format_on_save": "on",
        },

        "HTML": {
            "tab_size": 2,
            "format_on_save": "on",
            "language_servers": ["tailwindcss-language-server", "html-language-server"],
        },

        "CSS": {
            "tab_size": 2,
        },

        "SCSS": {
            "tab_size": 2,
        },

        "JavaScript": {
            "tab_size": 2,
            "format_on_save": "on",
        },

        "TypeScript": {
            "tab_size": 2,
            "format_on_save": "on",
        },

        "JSON": {
            "tab_size": 2,
        },

        "SQL": {
            "tab_size": 4,
        },
    },
    "lsp": {
        "intelephense": {
            "initialization_options": {
                "licenceKey": "",
                "storagePath": "~/.cache/intelephense",
                "clearCache": false,
            },
            "settings": {
                "files": {
                    "maxSize": 10000000,
                    "files": {
                        "maxSize": 5000000,
                    },
                    "associations": ["**/*.php", "**/*.php.default", "**/.description.php", "**/.parameters.php"],
                    "exclude": [
                        "**/.git/**",
                        "**/node_modules/**",
                        "**/vendor/**",
                        "**/bitrix/cache/**",
                        "**/bitrix/managed_cache/**",
                        "**/bitrix/stack_cache/**",
                        "**/bitrix/backup/**",
                        "**/upload/**",
                    ],
                },
                // Глобальное подключение ядра Битрикса для всех ваших проектов
                "environment": {
                    "includePaths": [
                        "/Users/ваш_юзер/Dev/bitrix_source/bitrix/modules/", // Укажите ваш абсолютный путь к ядру
                    ],
                },
                "diagnostics": {
                    "undefinedSymbols": false,
                    "undefinedFunctions": false,
                    "undefinedConstants": false,
                    "undefinedTypes": false,
                },
            },
        },
    },

    "language_models": {
        "ollama": {
            "api_url": "http://127.0.0.1:11434",
            "available_models": [
                {
                    "name": "qwen3-coder",
                    "max_tokens": 8192,
                },
            ],
        },
    },
}



================================================================================
          ШПАРГАЛКА ПО ZED + VIM + OLLAMA (ДЛЯ MANJARO LINUX / KDE PLASMA)
================================================================================

1. ПОИСК КОДА И НАВИГАЦИЯ ПО ПРОЕКТУ
--------------------------------------------------------------------------------
Хоткей в Manjaro   | Действие
--------------------------------------------------------------------------------
Ctrl + P           | Поиск файла по имени (Fuzzy finder)
Ctrl + Shift + F   | Глобальный поиск текста по всему проекту
Ctrl + F           | Поиск текста в текущем файле
/текст             | (В Vim) Поиск текста вперед по файлу
?текст             | (В Vim) Поиск текста назад по файлу
n / N              | (В Vim) Следующее / Предыдущее совпадение текста
Ctrl + Shift + O   | Переход к методу, функции или классу в файле (Outline)
Ctrl + B           | Показать / скрыть левую панель дерева файлов проекта
| F12 | Перейти к определению |
| Alt + ← | Назад |
| Alt + → | Вперед |
--------------------------------------------------------------------------------

2. ПЕРЕМЕЩЕНИЕ ПО КОДУ И ВКЛАДКАМ (NORMAL MODE В VIM)
--------------------------------------------------------------------------------
Команда            | Направление / Действие
--------------------------------------------------------------------------------
h / j / k / l      | Влево / Вниз / Вверх / Вправо
w / b              | На одно слово вперед / На одно слово назад
e                  | Переместить курсор в конец текущего слова
0 (ноль) / $       | Прыгнуть в самое начало строки / В самый конец строки
gg / G             | Переход в начало файла / Переход в конец файла
Ctrl + d / Ctrl + u| Прокрутка экрана на полстраницы Вниз / Вверх
%                  | Прыгнуть к парной скобке (круглые, фигурные, квадратные)
gt / gT            | Переключение на следующую / предыдущую вкладку (Tab)
| * | Найти слово под курсором |
| # | Найти слово назад |
| fX | До символа X |
| tX | Перед символом X |
| ; | Повтор f/t |
| , | Повтор в обратную сторону |
--------------------------------------------------------------------------------

3. ПРАВКА КОДА И ТЕКСТОВЫЕ ОБЪЕКТЫ (VIM-МАГИЯ ДЛЯ HTML/PHP/BLADE)
--------------------------------------------------------------------------------
Команда            | Результат выполнения (нажимать в Normal режиме после Esc)
--------------------------------------------------------------------------------
u / Ctrl + r       | Отмена действия (Undo) / Повтор отмененного действия (Redo)
dd / yy            | Удалить (вырезать) строку / Скопировать строку в буфер
p / P              | Вставить из буфера после курсора / Перед курсором
o / O              | Новая строка Снизу + режим ввода / Сверху + режим ввода
diw / ciw          | Удалить слово под курсором / Изменить слово под курсором
di" / ci"          | Удалить всё внутри кавычек "" / Изменить всё внутри ""
di' / ci'          | Удалить всё внутри кавычек '' / Изменить всё внутри ''
da" / ca"          | Удалить текст вместе с кавычками "" / Изменить вместе с ""
cit                | Изменить контент внутри HTML/Blade тега (очистить и писать)
dat                | Удалить HTML/Blade тег целиком вместе с его содержимым
yi" / yit          | Скопировать текст внутри кавычек / Скопировать текст внутри тега
| >> | Увеличить отступ |
| << | Уменьшить отступ |
| == | Автоотступ строки |
| =ap | Форматировать абзац |
--------------------------------------------------------------------------------

4. ВСТРОЕННЫЙ ТЕРМИНАЛ ZED
--------------------------------------------------------------------------------
Хоткей в Manjaro   | Действие
--------------------------------------------------------------------------------
Ctrl + `           | Открыть / скрыть встроенный терминал
Ctrl + Shift + T   | Открыть новую вкладку терминала в нижней панели
| Ctrl + Shift + C | Копировать |
| Ctrl + Shift + V | Вставить |
--------------------------------------------------------------------------------

5. ВЫЗОВ ИИ-АГЕНТА (OLLAMA / QWEN3-CODER)
--------------------------------------------------------------------------------
Хоткей в Manjaro   | Действие
--------------------------------------------------------------------------------
Ctrl + Alt + B     | Открыть / закрыть правую панель ИИ-чата (Assistant)
Ctrl + Enter       | Инлайн-генерация кода прямо в файле на месте курсора
                   | (Или отправка выделенного участка кода в контекст чата)
================================================================================
