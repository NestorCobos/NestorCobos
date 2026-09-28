# Configuración del perfil de GitHub — Nestor Cobos

## 1. Crear el repositorio especial

GitHub muestra el README del perfil cuando tienes un repositorio público con exactamente el mismo nombre que tu usuario:

`NestorCobos/NestorCobos`

Copia `README.md` y la carpeta `assets/` a ese repositorio.

## 2. Foto

La foto enviada por Nestor está incluida como:

`assets/profile.png`

## 3. Logo

El logo `NC` tecnológico está en:

`assets/logo-nc.svg`

## 4. Snake de contribuciones

El README intenta cargar:

`https://raw.githubusercontent.com/NestorCobos/NestorCobos/output/github-contribution-grid-snake-dark.svg`

Para generarlo automáticamente, crea:

`.github/workflows/snake.yml`

con:

```yaml
name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk@v3
        with:
          github_user_name: NestorCobos
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      - uses: crazy-max/ghaction-github-pages@v4
        with:
          build_dir: dist
        env:
          GH_PAT: ${{ secrets.GITHUB_TOKEN }}
```

## 5. Nota sobre estadísticas

Las tarjetas de estadísticas, racha, actividad y trofeos son imágenes generadas por servicios externos y se actualizan dinámicamente.

No se han escrito números manualmente para evitar mostrar estadísticas inventadas.

## 6. Contacto

Los datos públicos incluidos son los proporcionados por el propietario del perfil. No añadas contraseñas, tokens, claves API ni información privada al README.
