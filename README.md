# FORM-FB-01 · Fichas bibliográficas (Sistemas Distribuidos)

Actividad formativa individual previa a TA-IND-01: cinco fichas bibliográficas sobre arquitecturas de microservicios, escritas en LaTeX con referencias IEEE generadas por biblatex.

**Autor:** Erwin Daniel Bueno Troya, Ingeniería de Software, Universidad Técnica Estatal de Quevedo (UTEQ).

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `main.tex` | Archivo principal del documento |
| `fuentes.bib` | Base bibliográfica con las cinco fuentes y sus DOI |
| `main.pdf` | Documento compilado |
| `evidencias/compilacion-overleaf.png` | Captura del proyecto compilado en Overleaf |
| `README.md` | Este archivo |

## Cómo se compiló

El documento lo compilé en **Overleaf**, en el proyecto `FORM-FB-01`.

- **Compilador:** pdfLaTeX (el que trae Overleaf por defecto)
- **Archivo principal:** `main.tex`
- **Bibliografía:** biber, que Overleaf ejecuta solo porque el documento usa `biblatex` con `backend=biber`

Pasos en Overleaf:

1. Crear un proyecto en blanco y subir `main.tex` y `fuentes.bib`.
2. En *Menu → Settings*, revisar que el compilador sea `pdfLaTeX` y que el documento principal sea `main.tex`.
3. Presionar **Recompile**. Overleaf hace las pasadas de pdfLaTeX y biber en el orden correcto.
4. Descargar el PDF con el botón de descarga del visor.

![Compilación en Overleaf](evidencias/compilacion-overleaf.png)

## Compilar en una computadora (opcional)

Si se quiere compilar fuera de Overleaf, el orden de los comandos importa, porque biber necesita el archivo `.bcf` que genera la primera pasada:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

Otra opción es usar `latexmk -pdf main.tex`, que hace todas las pasadas solo.

### Dependencias

- Una distribución de LaTeX: TeX Live 2022 o posterior, o MiKTeX.
- `biber`, que es el backend bibliográfico de biblatex (no se usa BibTeX).
- Paquetes LaTeX: `biblatex`, `biblatex-ieee`, `babel` con idioma `spanish`, `csquotes`, `hyperref`, `geometry`, `enumitem`, `parskip`, `lmodern`.

En Debian o Ubuntu se instalan con:

```bash
sudo apt-get install texlive-latex-extra texlive-bibtex-extra texlive-lang-spanish biber latexmk
```

En Overleaf todos estos paquetes ya vienen instalados.

## Fuentes

| Clave | Fuente | DOI |
|---|---|---|
| `abgaz2023` | Abgaz et al., *IEEE Transactions on Software Engineering*, 2023 | [10.1109/TSE.2023.3287297](https://doi.org/10.1109/TSE.2023.3287297) |
| `velepucha2023` | Velepucha y Flores, *IEEE Access*, 2023 | [10.1109/ACCESS.2023.3305687](https://doi.org/10.1109/ACCESS.2023.3305687) |
| `oumoussa2024` | Oumoussa y Saidi, *IEEE Access*, 2024 | [10.1109/ACCESS.2024.3365079](https://doi.org/10.1109/ACCESS.2024.3365079) |
| `blinowski2022` | Blinowski, Ojdowska y Przybyłek, *IEEE Access*, 2022 | [10.1109/ACCESS.2022.3152803](https://doi.org/10.1109/ACCESS.2022.3152803) |
| `li2021` | Li et al., *Information and Software Technology*, 2021 | [10.1016/j.infsof.2020.106449](https://doi.org/10.1016/j.infsof.2020.106449) |
