# Liquid Glass Safari Optimized for Home Assistant

Safari-focused Liquid Glass theme for Home Assistant dashboards on iPhone, iPad, and macOS.

<img width="500" alt="Liquid Glass light preview" src="https://github.com/user-attachments/assets/c60d760b-4531-41c2-b8b5-47404e8743d7" /><img width="500" alt="Liquid Glass dark preview" src="https://github.com/user-attachments/assets/273f0e86-180e-42b3-abe0-bab25c359584" />

## HACS Custom Repository

1. Open HACS in Home Assistant.
2. Open the custom repositories dialog.
3. Add this repository URL:

```text
https://github.com/tukies/HAOS_LiquidGlass
```

4. Set the category to `Theme`.
5. Download `Liquid Glass Safari Optimized`.
6. Reload themes or restart Home Assistant.
7. Select the `Liquid Glass Safari Optimized` theme from your user profile.

You can also open the repository flow directly:

[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=tukies&repository=HAOS_LiquidGlass&category=theme)

## Home Assistant Setup

Themes need to be enabled in `configuration.yaml`:

```yaml
frontend:
  themes: !include_dir_merge_named themes
```

After changing `configuration.yaml`, restart Home Assistant. After theme updates, use the `frontend.reload_themes` action or restart.

## Full Glass Rendering

The theme uses Home Assistant theme variables plus global card styles through card-mod-compatible theme hooks. Install either `card-mod` or [`uix`](https://github.com/Lint-Free-Technology/uix) through HACS for the full glass card and sidebar treatment.

> [!NOTE]
> If you use `uix` for the transparent sidebar, remember to [add its UI extension service](https://uix.lf.technology/quick-start/#add-ui-extension-service) after installing the integration — installing it from HACS alone is not enough.

The CSS intentionally avoids SVG displacement filters and WebGL effects because this theme is targeted at Safari/WebKit.

## Default Theme Automation

```yaml
alias: Frontend - Set Liquid Glass Safari Optimized theme
trigger:
  - platform: homeassistant
    event: start
action:
  - service: frontend.set_theme
    data:
      name: Liquid Glass Safari Optimized
```

## Credits

Forked from [Nezz/homeassistant-visionos-theme](https://github.com/Nezz/homeassistant-visionos-theme).

Based on [Bas Nijholt's iOS Themes](https://github.com/basnijholt/lovelace-ios-themes).

Dropdown fixes from [Wessam Lauf's Frosted Glass Theme](https://github.com/wessamlauf/homeassistant-frosted-glass-themes).
