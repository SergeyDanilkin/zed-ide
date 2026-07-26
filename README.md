# zed-ide

#Plugins
<ul>
  <li>Html</li>
  <li>Sql</li>
  <li>Php</li>
  <li>Scss & Sass</li>
  <li>Xml</li>
  <li>Emmet</li>
  <li>Tailwind Syntax</li>
  <li>Blade</li>
  <li>Json5</li>
  <li>HTML Snippets</li>
  <li>Javascript Snippets</li>
  <li>Php Snippets</li>
  <li>Laravel</li>
  <li>Catppuccin</li>
  <li>Catppuccin Icons</li>
</ul>

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
                    "command": "bash",
                    "arguments": [
                        "-c",
                        "cat > {buffer_path} && ./vendor/bin/pint --quiet {buffer_path} && cat {buffer_path}",
                    ],
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
