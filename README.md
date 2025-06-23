# AdminLTE4 + Thymeleaf + Bootstrap 5 + WebJars

Este proyecto es una base de aplicación web moderna que combina las siguientes tecnologías:

- ✅ Spring Boot 3.5.3
- ✅ Thymeleaf como motor de plantillas
- ✅ Bootstrap 5 para estilos
- ✅ AdminLTE 4 para el dashboard
- ✅ Boostrap Icons y FontAwesome para iconos
- ✅ WebJars para gestionar dependencias front-end
- ✅ Thymeleaf Layout Dialect para diseño modular con herencia

Ideal para crear interfaces administrativas o portales empresariales de forma rápida, limpia y escalable.

---

## 🚀 ¿Cómo empezar?

Este proyecto ya está configurado y listo para usar. Solo necesitas abrirlo en tu IDE y ejecutar la clase principal con Spring Boot.

Para crear una nueva vista, puedes usar como base el archivo:

```
src/main/resources/templates/web/blank_page.html
```

---

## 🧩 ¿Cómo funciona el Layout?

El archivo base `layout/base.html` contiene la estructura principal de la app. Las vistas hijas heredan esta estructura mediante:

```html
<html layout:decorate="~{layout/base}">
```

Los siguientes `layout:fragment` te permiten definir contenido dinámico por vista:

| Fragmento          | Ubicación       | Propósito                                                    |
|--------------------|-----------------|--------------------------------------------------------------|
| `<head> <title>..` | `<head><title>` | Define el título del navegador                               |
| `title`            | `<h3>`          | Título dentro de la vista principal                          |
| `title_parent`     | Breadcrumb      | Texto del padre (ej: Home)                                   |
| `title_child`      | Breadcrumb      | Texto del hijo actual (ej: Dashboard)                        |
| `<div layout:fragment="content"> `          | `<div>`        | Contenido principal de la vista                              |

---

## 📝 Ejemplo de `blank_page.html`

```html
<!DOCTYPE html>
<html lang="es"
      xmlns:th="http://www.thymeleaf.org"
      xmlns:layout="http://www.ultraq.net.nz/thymeleaf/layout"
      layout:decorate="~{layout/base}">

<body>
  <h3 layout:fragment="title">Inicio Home</h3>
  <a href="#" layout:fragment="title_parent">Home</a><span layout:fragment="title_child">Dashboard</span>

  <div layout:fragment="content">         
        <p>Contneido aaquí</p>      
  </div>
</body>
</html>
```

---

## 📂 Estructura del Proyecto

```
src
└── main
    └── java
    └── resources
        ├── static/
        │   └── imágenes, CSS personalizados (Si no utilizas WebJars)
        └── templates/
            ├── fragments/
            │   ├── navbar.html (Barra de navegación superior de AdminLTE)
            │   ├── aside.html (Menu lateral de AdminLTE)
            │   └── footer.html (Pie de página de AdminLTE)
            ├── layout/
            │   └── base.html (Estructura base de la app con decorate de Thymeleaf) 
            └── web/
                └── index.html (Página de inicio, ejemplo de dashboard)
                └── blank_page.html (Plantilla de página en blanco)
```

---

## 📦 Dependencias Clave

- `spring-boot-starter-thymeleaf`
- `thymeleaf-layout-dialect`
- `admin-lte` vía WebJars
- `bootstrap`, `fontawesome`, `overlayscrollbars`, `apexcharts` y más...

Las versiones están centralizadas en `pom.xml` para facilitar el mantenimiento.

---

## 📚 Recursos útiles

- [Spring Boot DevTools](https://docs.spring.io/spring-boot/3.5.3/reference/using/devtools.html)
- [Thymeleaf Template Engine](https://docs.spring.io/spring-boot/3.5.3/reference/web/servlet.html#web.servlet.spring-mvc.template-engines)
- [Thymeleaf Layout Dialect](https://ultraq.github.io/thymeleaf-layout-dialect/)
- [WebJars](https://www.webjars.org/)
- [AdminLTE Docs](https://adminlte.io/docs/4.0/)

---

 

## ⚖️ Licencia

Este proyecto está licenciado bajo la licencia MIT. Puedes usarlo libremente en proyectos personales o empresariales.
