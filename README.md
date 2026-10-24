# Portfolio Shooter

Hero Shooter desarrollado en Unreal Engine 5 íntegramente con Blueprints.

Este proyecto está centrado en la creación de sistemas modulares y escalables para habilidades y armas, priorizando una arquitectura data-driven que permita crear nuevos personajes y armamento sin modificar la lógica existente.

## Tecnologías

- Unreal Engine 5
- Blueprints
- Data Assets
- Data Tables
- Object Strategies
- Arquitectura Data-Driven

## Características principales

### Sistema de armas Data-Driven

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

## Capturas

_Añadir imágenes del juego aquí._

## Gameplay

_Añadir enlace a vídeo o demo._

## Autor

Desarrollado por Álvaro.
