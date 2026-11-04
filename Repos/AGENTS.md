# Repos

> **TL;DR:** Índice de los repositorios clonados. Git del espacio de trabajo ignora esta carpeta salvo `Repos/AGENTS.md`; cada clon conserva su propio control de versiones.

## Propósito

Aquí viven los clones del código. Este archivo es el índice: dice qué hay, de dónde salió y para qué se usa. El código no se versiona en el repositorio del espacio de trabajo.

La regla de exclusión está en `.gitignore` con el mismo nombre de archivo que estas instrucciones: se ignora `/Repos/*` y se vuelve a incluir `!/Repos/AGENTS.md`.

## Clones

| Carpeta | Producto | Remoto | Rama | Para qué |
| --- | --- | --- | --- | --- |
| [lab5paradigmas/](lab5paradigmas/) | UNA Chat | https://github.com/Camilo-FG/lab5paradigmas.git | `main` | Laboratorio 5. El Laboratorio 8 continúa aquí con la historia US-01 (Auth0). |

Descubierto el 2026-10-28 desde el checkout local `Paradigmas/Lab5/despues`, que ya apuntaba a ese remoto y estaba al día con `origin/main` (`c39a1b8`).

## Qué no poner aquí

- Notas durables del proyecto: van en [../Knowledge/AGENTS.md](../Knowledge/AGENTS.md) y en el cerebro `brain/` del espacio de trabajo.
- Procedimientos reutilizables: van en [../Skills/AGENTS.md](../Skills/AGENTS.md).
