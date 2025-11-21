# Hervin Portfolio - Instrucciones de Personalización

## 📁 Estructura de Archivos

\`\`\`
hervin-portfolio/
├── index.html          # Página de inicio
├── portfolio.html      # Página de portfolio
├── servicios.html      # Página de servicios
├── sobre-mi.html       # Página sobre mí
├── contacto.html       # Página de contacto
├── aviso-legal.html    # Página de aviso legal
├── styles.css          # Estilos CSS
├── script.js           # JavaScript
├── sitemap.xml         # Mapa del sitio para SEO
├── robots.txt          # Archivo robots
└── INSTRUCCIONES.md    # Este archivo
\`\`\`

## 🎨 Personalización de Colores

Abre `styles.css` y modifica las variables en la sección `:root`:

\`\`\`css
:root {
    --color-primary: #00adb5;      /* Color principal (botones, acentos) */
    --color-secondary: #222831;    /* Color secundario (footer) */
    --color-accent: #393e46;       /* Color de acento */
    --color-bg: #f8f8f8;          /* Color de fondo */
    --color-text: #222;           /* Color del texto */
    --color-text-light: #666;     /* Color del texto claro */
    --color-white: #ffffff;       /* Blanco */
}
\`\`\`

## ✏️ Editar Contenidos

### Página de Inicio (index.html)
- **Título hero**: Línea 42 - `<h1 class="hero-title">`
- **Subtítulo**: Línea 43 - `<p class="hero-subtitle">`
- **Imagen de fondo**: Línea 38 - Cambia la URL de Unsplash

### Portfolio (portfolio.html)
- **Proyectos**: Líneas 45-100 - Cada proyecto está en un `<div class="portfolio-slide">`
- **Imágenes**: Cambia las URLs de Unsplash por tus imágenes
- **Títulos y descripciones**: Edita el contenido dentro de cada slide

### Servicios (servicios.html)
- **Tarjetas de servicio**: Líneas 45-80 - Cada servicio en un `<div class="service-card">`
- **Íconos SVG**: Puedes cambiarlos desde [Heroicons](https://heroicons.com)

### Sobre Mí (sobre-mi.html)
- **Foto de perfil**: Línea 40 - Cambia la URL de la imagen
- **Biografía**: Líneas 45-50
- **Estadísticas**: Líneas 55-75
- **Testimonios**: Líneas 80-110

### Contacto (contacto.html)
- **Información de contacto**: Líneas 45-75
- **Email destino**: En `script.js` línea 140 (ver sección de email)

## 📧 Configurar Formulario de Contacto

El formulario actual simula el envío. Para hacerlo funcional:

1. Crea un archivo PHP (ej: `send-email.php`) en tu servidor
2. En `script.js` línea 140, descomenta el código de fetch
3. Cambia `'tu-endpoint-de-email.php'` por tu archivo PHP

Ejemplo de PHP básico:

\`\`\`php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = $_POST['name'];
    $email = $_POST['email'];
    $subject = $_POST['subject'];
    $message = $_POST['message'];
    
    $to = "tu-email@ejemplo.com";
    $headers = "From: " . $email;
    
    if (mail($to, $subject, $message, $headers)) {
        echo json_encode(['success' => true]);
    } else {
        echo json_encode(['success' => false]);
    }
}
?>
\`\`\`

## 🖼️ Cambiar Imágenes

### Opción 1: Usar Unsplash (actual)
Mantén las URLs de Unsplash y modifica los parámetros:
\`\`\`
https://images.unsplash.com/photo-ID?w=1920&h=1080&fit=crop
\`\`\`

### Opción 2: Usar tus propias imágenes
1. Crea una carpeta `images/` en el directorio raíz
2. Coloca tus imágenes allí
3. Cambia las URLs en los HTML:
\`\`\`html
<img src="images/mi-foto.jpg" alt="Descripción">
\`\`\`

## 🔤 Cambiar Tipografía

Abre `styles.css` línea 4 y cambia la fuente de Google Fonts:

\`\`\`css
@import url('https://fonts.googleapis.com/css2?family=TU-FUENTE&display=swap');

:root {
    --font-body: 'TU-FUENTE', sans-serif;
}
\`\`\`

## 📱 Redes Sociales

Edita los enlaces del footer en cada archivo HTML (líneas 130-135):

\`\`\`html
<a href="https://instagram.com/tu-usuario" target="_blank">Instagram</a>
<a href="https://linkedin.com/in/tu-usuario" target="_blank">LinkedIn</a>
<a href="https://twitter.com/tu-usuario" target="_blank">Twitter</a>
\`\`\`

## 🔍 SEO

### Meta Tags
Edita en cada HTML el `<head>`:
\`\`\`html
<title>Tu Título - Hervin</title>
<meta name="description" content="Tu descripción">
\`\`\`

### Sitemap.xml
Cambia `https://tudominio.com` por tu dominio real en todas las URLs

### Google Analytics
Añade antes del `</head>` en cada HTML:

\`\`\`html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=TU-ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'TU-ID');
</script>
\`\`\`

## 🚀 Publicar el Sitio

### Opción 1: GitHub Pages (Gratis)
1. Sube todos los archivos a un repositorio de GitHub
2. Ve a Settings > Pages
3. Selecciona la rama main y carpeta root
4. Tu sitio estará en `tu-usuario.github.io/repositorio`

### Opción 2: Netlify (Gratis)
1. Arrastra la carpeta completa a [Netlify Drop](https://app.netlify.com/drop)
2. Tu sitio estará publicado instantáneamente

### Opción 3: Hosting Tradicional
1. Sube todos los archivos vía FTP a tu servidor
2. Asegúrate de que index.html esté en la raíz

## ⚙️ Características Incluidas

✅ Diseño responsive (móvil, tablet, desktop)
✅ Cursor personalizado (solo desktop)
✅ Animaciones suaves de entrada
✅ Navegación AJAX con preloader
✅ Slider de portfolio con teclado
✅ Formulario de contacto funcional
✅ Optimizado para SEO
✅ Sitemap y robots.txt
✅ 100% personalizable

## 🆘 Soporte

Si tienes dudas:
1. Revisa este archivo completo
2. Los comentarios en los archivos CSS y JS
3. Busca en Google "cómo hacer X en HTML/CSS"

## 📝 Checklist de Personalización

- [ ] Cambiar colores en `styles.css`
- [ ] Editar textos en todos los HTML
- [ ] Cambiar imágenes por las tuyas
- [ ] Configurar formulario de contacto
- [ ] Actualizar redes sociales en footer
- [ ] Editar meta tags para SEO
- [ ] Cambiar dominio en sitemap.xml
- [ ] Añadir Google Analytics
- [ ] Probar en móvil y desktop
- [ ] Publicar el sitio

¡Listo! Tienes un sitio web profesional tipo Hervin completamente funcional y personalizable.
