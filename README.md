# Actividad-3-Bootstrap-y-WAI-ARIA
Este proyecto incluye cinco elementos de Bootstrap, cada uno presentado en su versión original y mejorada con atributos WAI-ARIA para mejorar la accesibilidad.

## Elementos Seleccionados

1. Botón
2. Menú Desplegable
3. Alerta
4. Pestañas
5. Modal

## 1. Botón

- **Código Original**: 
  ```html
  <button type="button" class="btn btn-primary">Enviar</button>
  ```

- **Código mejorado***:
```html
<button type="button" class="btn btn-primary" aria-label="Enviar formulario">Enviar</button>
```

**Mejora** : Se agregó aria-label para proporcionar una descripción más clara del propósito del botón, mejorando la comprensión para los usuarios de lectores de pantalla.

## 2. Menú Desplegable : 

- **Código Original**: 
  ```html
   <div class="dropdown">
    <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-bs-toggle="dropdown" aria-expanded="false">
        Dropdown
    </button>
    <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton">
        <li><a class="dropdown-item" href="#">Acción 1</a></li>
        <li><a class="dropdown-item" href="#">Acción 2</a></li>
    </ul>
  </div>
  ```

- **Código mejorado***:
```
  <div class="dropdown" role="menu">
    <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        Dropdown
    </button>
    <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton" role="menu">
        <li role="menuitem"><a class="dropdown-item" href="#">Acción 1</a></li>
        <li role="menuitem"><a class="dropdown-item" href="#">Acción 2</a></li>
    </ul>
</div>
```

**Mejora** : Se agregó role="menu" al contenedor del menú y role="menuitem" a cada elemento de la lista. También se añadió aria-haspopup="true" al botón para indicar que tiene un menú desplegable asociado.


## 3. Alerta

- **Código Original**: 
  ```html
   <div class="alert alert-warning" role="alert">
    Este es un mensaje de advertencia.
  </div>
  ```

- **Código mejorado***:
```
  <div class="alert alert-warning" role="alert" aria-live="assertive" aria-atomic="true">
    Este es un mensaje de advertencia.
</div>
```

**Mejora** : Se añadieron aria-live="assertive" y aria-atomic="true" para asegurar que el mensaje de alerta sea anunciado inmediatamente por los lectores de pantalla y que se lea en su totalidad.

## 4. Pestañas

- **Código Original**: 
  ```html
   <ul class="nav nav-tabs" id="myTab" role="tablist">
    <li class="nav-item">
        <a class="nav-link active" id="home-tab" data-bs-toggle="tab" href="#home" role="tab" aria-controls="home" aria-selected="true">Inicio</a>
    </li>
    <li class="nav-item">
        <a class="nav-link" id="profile-tab" data-bs-toggle="tab" href="#profile" role="tab" aria-controls="profile" aria-selected="false">Perfil</a>
    </li>
  </ul>
  <div class="tab-content" id="myTabContent">
      <div class="tab-pane fade show active" id="home" role="tabpanel" aria-labelledby="home-tab">Contenido de Inicio</div>
      <div class="tab-pane fade" id="profile" role="tabpanel" aria-labelledby="profile-tab">Contenido de Perfil</div>
  </div>
  ```

- **Código mejorado***:
```
  <ul class="nav nav-tabs" id="myTab" role="tablist" aria-label="Pestañas de navegación">
    <li class="nav-item" role="presentation">
        <a class="nav-link active" id="home-tab" data-bs-toggle="tab" href="#home" role="tab" aria-controls="home" aria-selected="true">Inicio</a>
    </li>
    <li class="nav-item" role="presentation">
        <a class="nav-link" id="profile-tab" data-bs-toggle="tab" href="#profile" role="tab" aria-controls="profile" aria-selected="false">Perfil</a>
    </li>
</ul>
<div class="tab-content" id="myTabContent">
    <div class="tab-pane fade show active" id="home" role="tabpanel" aria-labelledby="home-tab">Contenido de Inicio</div>
    <div class="tab-pane fade" id="profile" role="tabpanel" aria-labelledby="profile-tab">Contenido de Perfil</div>
</div>
```

**Mejora** : Se añadió aria-label="Pestañas de navegación" al contenedor de las pestañas para proporcionar contexto a los usuarios de tecnologías asistivas. Además, se agregó role="presentation" a los elementos de la lista para indicar que no tienen un papel semántico en la estructura del documento.


## 5. Modal

- **Código Original**: 
  ```html
   <div class="modal" tabindex="-1">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title">Título del modal</h5>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Cerrar"></button>
            </div>
            <div class="modal-body">
                <p>Contenido del modal...</p>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cerrar</button>
                <button type="button" class="btn btn-primary">Guardar cambios</button>
            </div>
        </div>
    </div>
  </div>
  ```

- **Código mejorado***:
```
  <div class="modal" tabindex="-1" role="dialog" aria-labelledby="modalTitle" aria-describedby="modalDescription">
    <div class="modal-dialog" role="document">
        <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title" id="modalTitle">Título del modal</h5>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Cerrar"></button>
            </div>
            <div class="modal-body" id="modalDescription">
                <p>Contenido del modal...</p>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cerrar</button>
                <button type="button" class="btn btn-primary">Guardar cambios</button>
            </div>
        </div>
    </div>
</div>
```

**Mejora** : Se añadieron role="dialog" para indicar que es un modal, aria-labelledby para asociar el título del modal y aria-describedby para proporcionar una descripción del contenido del modal. Esto mejora la accesibilidad al permitir que los usuarios de tecnologías asistivas comprendan mejor el propósito y
