# Guía rápida: Cómo añadir recursos a mi libro

Este archivo sirve como referencia para añadir **archivos multimedia** a tu web de MkDocs: PDFs, imágenes y videos.

---
## Estilos

### <span style="color:#e67600;">🌐 ISO 31000</span>
Para poner por ejemplo un título de color naranja


## 📄 PDFs

- **Opción 1: Enlace para abrir o descargar**
```markdown
[Ver PDF de ejemplo](assets/mi-documento.pdf)
```

- **Opción 2: Incrustar en la página**
```html
<iframe src="assets/mi-documento.pdf" width="100%" height="600px"></iframe>
```

> Consejo: Usa la opción de enlace para PDFs grandes o protegidos.

---

## 🖼️ Imágenes (PNG, JPG, GIF)

- Insertar imagen simple:
```markdown
![Descripción de la imagen](assets/mi-imagen.png)
```

- Ajustar tamaño con HTML:
```html
<img src="assets/mi-imagen.png" alt="Descripción" width="500">
```

---

## 🎬 Videos (MP4)

- Insertar video con controles:
```html
<video width="640" height="360" controls>
  <source src="assets/mi-video.mp4" type="video/mp4">
  Tu navegador no soporta video HTML5.
</video>
```

> Consejo: Optimiza videos (resolución y peso) y evita archivos enormes para no saturar GitHub Pages.

---

## 🗂️ Ubicación de los archivos

- Todos los archivos se colocan en `docs/assets/`.
- Evita moverlos después de crear enlaces, para que no rompan la web.

---

## ✅ Flujo recomendado

1. Coloca el archivo en `docs/assets/`.
2. Inserta el enlace o incrústalo en el `.md` correspondiente.
3. Prueba localmente con:

```bash
mkdocs serve
```

4. Si todo funciona, haz commit y push:

```bash
git add .
git commit -m "Añadido recurso nuevo"
git push
```

5. Finalmente, actualiza la web en GitHub Pages:

```bash
mkdocs gh-deploy
```

---

💡 **Tip:**  
Puedes usar este archivo como plantilla para futuros recursos.  
Añade capturas de pantalla, miniaturas o ejemplos para que te quede todavía más visual.
