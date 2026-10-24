# Portfolio Shooter

Demo técnica desarrollada íntegramente en Blueprints en Unreal Engine 5.

El objetivo del proyecto no es crear un juego completo, sino diseñar y validar una arquitectura de gameplay modular y escalable para Hero Shooters.

La demo se centra en la creación de un sistema de armas completamente data-driven basado en Gameplay Tags, Data Assets y Object Strategies, permitiendo construir nuevos personajes, armas y modos de disparo sin modificar los sistemas existentes.

## Principios de Diseño

Cero Ticks / Cero Hard Casts

Todo el sistema se basa en:

Eventos
Interfaces
Delegados
La lógica principal evita el uso de Tick y elimina dependencias rígidas mediante Hard Casts.

Composición sobre Herencia
La arquitectura utiliza Object Strategies y componentes modulares en lugar de jerarquías de clases complejas.

Nuevos comportamientos pueden crearse mediante composición de estrategias sin modificar sistemas existentes.

Data-Driven First
Las armas se construyen configurando datos y no escribiendo lógica específica.

Añadir una nueva arma generalmente consiste en:

Crear un Weapon Data Asset.
Configurar los Fire Modes.
Seleccionar Trigger, Execution y Reload Strategies.
Ajustar parámetros de balance.
Sin necesidad de modificar el sistema de armas.

## Tecnologías

- Unreal Engine 5
- Blueprints
- Data Assets
- Data Tables
- Object Strategies
- Arquitectura Data-Driven

# Características principales

## Arquitectura

```text
Character
│
├── Equipped Weapon Data Asset
│
└── Weapon Manager Component
     │
     ▼
     Weapon Data Asset
     │
     ├── Weapon Name
     ├── Reload Animation
     │
     └── TMap<GameplayTag, FireModeConfig>
           │
           ├── Primary Fire
           ├── Secondary Fire
           └── Special Fire
                │
                ▼
           FireModeConfig
                │
                ├── Trigger Class
                ├── Execution Class
                ├── Reload Class
                ├── Range
                ├── Fire Rate
                ├── Bullets Per Shot
                ├── Damage
                ├── Spread Config
                └── Reload Config
```

## Sistema de armas Data-Driven

Todo el comportamiento de las armas está definido mediante datos y estrategias configurables.

Cada arma puede combinar distintos módulos de comportamiento sin necesidad de crear nuevas clases específicas.

La arquitectura se basa en tres tipos principales de estrategias:

- Trigger Strategies
  - Determinan cuándo se dispara un arma.
  - Ejemplos: automático, semiautomático, carga, ráfaga.

- Execution Strategies
  - Determinan cómo se ejecuta el disparo.
  - Ejemplos: proyectil, hitscan, multi-proyectil, efectos especiales.

- Reload Strategies
  - Determinan cómo se recargan los recursos del arma.
  - Ejemplos: recarga completa, individual, por energía o personalizada.

### Personajes con armamento único

Cada héroe posee armas exclusivas con comportamientos completamente configurables.

Los personajes no requieren lógica específica para sus armas, ya que el sistema obtiene toda la información de los datos configurados para cada equipamiento.

### Múltiples modos de disparo simultáneos

Las armas pueden disponer de uno o varios modos de disparo activos al mismo tiempo.

Cada modo de disparo mantiene de forma independiente:

- Configuración de daño.
- Cadencia.
- Consumo de recursos.
- Sistema de calor.
- Sistema de enfriamiento.
- Dispersión.
- Munición.
- Recarga.

Esto permite crear armas complejas con comportamientos híbridos.

### Sistema de calor y enfriamiento

Cada modo de disparo incorpora un sistema independiente de generación y disipación de calor.

La evolución del calor y el enfriamiento se controla mediante curvas configurables, permitiendo ajustar fácilmente:

- Velocidad de calentamiento.
- Velocidad de enfriamiento.
- Penalizaciones por sobrecalentamiento.
- Comportamiento específico de cada arma.

### Sistema de precisión configurable

Cada modo de disparo dispone de un sistema de dispersión configurable mediante un sesgo de centralidad.

Esto permite controlar matemáticamente la distribución de impactos y definir desde armas extremadamente precisas hasta armas con gran dispersión.

### Sistema de munición basado en Pools

La munición no depende de cargadores tradicionales.

Cada modo de disparo puede consumir recursos de pools compartidos o independientes.

Esto permite implementar:

- Munición convencional.
- Energía.
- Recursos regenerativos.
- Recursos compartidos entre armas o habilidades.

### Sistema de recarga simultánea

Los distintos modos de disparo de un arma pueden recargarse simultáneamente.

Cada modo mantiene su propia lógica, tiempos y recursos, permitiendo comportamientos complejos imposibles de conseguir con sistemas de cargador tradicionales.

## Objetivos del proyecto

- Diseñar sistemas escalables y reutilizables.
- Demostrar capacidades avanzadas de Blueprints.
- Aplicar principios de arquitectura modular.
- Reducir dependencias entre gameplay y contenido.
- Facilitar la creación de nuevos personajes mediante configuración de datos.

## Qué demuestra este proyecto

- Diseño de arquitecturas data-driven.
- Gameplay systems development en Blueprints.
- Uso avanzado de Gameplay Tags.
- Patrones de composición mediante Object Strategies.
- Desarrollo desacoplado mediante interfaces y delegados.
- Diseño modular orientado a extensibilidad.
- Principios de mantenimiento y escalabilidad.
- 
## Capturas Técnicas

### Weapon Data Asset

[Imagen]

### Weapon Manager Component

[Imagen]

### Fire Mode Configuration

[Imagen]

### Trigger Strategy

[Imagen]

### Execution Strategy

[Imagen]

### Reload Strategy

[Imagen]
## Gameplay

_Añadir enlace a vídeo o demo._

## Autor

Desarrollado por Álvaro de la Fuente.
