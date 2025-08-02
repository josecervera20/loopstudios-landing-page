# Frontend Mentor - Solución para Loopstudios Landing Page ✨

Esta es una solución al desafío [Loopstudios landing page challenge en Frontend Mentor](https://www.frontendmentor.io/challenges/loopstudios-landing-page-N88J5Onjw). Los desafíos de Frontend Mentor te ayudan a mejorar tus habilidades de codificación construyendo proyectos realistas.

## Tabla de Contenidos 📋

- [Resumen 📝](#resumen-📝)
  - [El desafío](#el-desafío)
  - [Captura de pantalla 📸](#captura-de-pantalla-📸)
  - [Enlace 🔗](#enlace-🔗)
- [Mi Proceso 🚀](#mi-proceso-🚀)
  - [Construido con 🏗️](#construido-con-🏗️)
  - [Lo que aprendí 🧠](#lo-que-aprendí-🧠)
  - [Desarrollo Continuo 📈](#desarrollo-continuo-📈)
  - [Recursos Útiles 📚](#recursos-útiles-📚)
- [Autor 🧑‍💻](#autor-🧑‍💻)
- [Agradecimientos 🙌](#agradecimientos-🙌)

## Resumen 📝

### El desafío

Los usuarios deberían poder:

- Ver el diseño óptimo del sitio dependiendo del tamaño de la pantalla de su dispositivo.
- Ver los estados hover para todos los elementos interactivos de la página.

### Captura de pantalla 📸

![Captura de pantalla de la solución de Loopstudios landing page](./design/desktop-design.jpg)

### Enlace 🔗

- URL de la Solución (Repositorio): [https://github.com/josecervera20/loopstudios-landing-page](https://github.com/josecervera20/loopstudios-landing-page)

## Mi Proceso 🚀

### Construido con 🏗️

- Marcado semántico HTML5
- Propiedades personalizadas de CSS (Variables CSS)
- **CSS Grid** (para todos los layouts responsivos y complejos)
- Enfoque Mobile-first
- Google Fonts: _Josefin Sans_ y _Alata_

### Lo que aprendí 🧠

Durante este proyecto, me enfoqué en el uso de CSS Grid para toda la maquetación y depuré en detalle los efectos `hover`, lo que me permitió profundizar en varios aspectos clave del desarrollo front-end.

- **Maquetación con CSS Grid (Layouts complejos)**: Utilicé `display: grid` y `grid-template-areas` para construir layouts que se adaptaran perfectamente a diferentes tamaños de pantalla. Por ejemplo, en la sección "leader", logré que la imagen y el texto se superpusieran de manera precisa en la versión de escritorio, asignando las celdas de la cuadrícula de forma estratégica.

  ```css
  /* Ejemplo de CSS Grid para la sección .leader */
  .leader {
    display: grid;
    gap: 2.5em;
  }

  @media (min-width: 768px) {
    .leader {
      grid-template-columns: repeat(7, 1fr);
      grid-template-rows: repeat(5, 1fr);
      gap: 0;
    }
    .leader__picture {
      grid-column: 1 / 5;
      grid-row: 1 / 5;
    }
    .leader__texts {
      grid-column: 4 / 8;
      grid-row: 3 / 6;
    }
  }
  ```

- **Implementación de Efectos Hover avanzados**: El mayor desafío fue la creación de la línea de subrayado animada para los enlaces. Para que funcionara correctamente, fue necesario asegurar la posición del pseudo-elemento `::after` con respecto a su padre, el enlace `<a>`.

  - **Pseudo-elementos y Posicionamiento**: La clave fue usar `position: relative` en el elemento `<a>` y `position: absolute` en `::after`. Esto permitió que la línea se posicionara dentro de los límites del enlace.
  - **Animación y Transición**: La línea se crea con `width: 0;` y se centra usando `transform: translateX(-50%);`. Al hacer `hover`, la propiedad `width` cambia a `25px`, y la transición hace que esta animación sea suave.

  ```css
  /* Ejemplo de hover para enlaces de navegación */
  .nav__link {
    position: relative;
    transition: color 0.3s ease;
  }

  .nav__link::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 50%;
    width: 0;
    height: 2px;
    background: var(--white);
    transform: translateX(-50%);
    transition: width 0.3s ease;
  }

  .nav__link:hover::after {
    width: 25px;
  }
  ```

- **Uso de la propiedad `inset`**: En la versión móvil, utilicé la propiedad `inset` (`inset: 0;`) para posicionar el menú de navegación en lugar de las cuatro propiedades (`top`, `bottom`, `left`, `right`). Esto demuestra una sintaxis más moderna y concisa.

### Desarrollo Continuo 📈

Me gustaría seguir profundizando en:

- **Accesibilidad (ARIA):** Implementar atributos ARIA en la navegación y otros componentes interactivos para mejorar la experiencia de usuario para todos.
- **Optimización de Rendimiento**: Aprender a optimizar los assets (imágenes, fuentes) y el código CSS para reducir los tiempos de carga de la página.
- **Animaciones complejas**: Explorar animaciones más avanzadas usando `@keyframes` y `transform` para añadir un mayor nivel de dinamismo.

### Recursos Útiles 📚

- [Frontend Mentor](https://www.frontendmentor.io/) - Una plataforma excelente para desafíos de codificación.
- [The Markdown Guide](https://www.markdownguide.org/) - Una referencia útil para la sintaxis de Markdown.
- [MDN Web Docs](https://developer.mozilla.org/es/docs/Web) - Siempre una fuente invaluable para entender las propiedades CSS y el funcionamiento de HTML.

## Autor 🧑‍💻

- GitHub - [@josecervera20](https://github.com/josecervera20)

## Agradecimientos 🙌

Agradezco a la comunidad de Frontend Mentor por proporcionar desafíos tan valiosos y a los recursos en línea como MDN por ser fuentes invaluables durante el desarrollo.
