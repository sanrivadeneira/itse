# itse
Estructuración del Repositorio y Desarrollo del Módulo Core
Descripcion el proyecto y cómo instalarlo
## Protección contra fuerza bruta (Rate Limiting)

Se incluye un `InMemoryRateLimiter` para desarrollo y pruebas, y un `RedisRateLimiter` diseñado para producción distribuida.

Política por defecto:
- max_attempts: 5 intentos fallidos en `window_seconds` (ej. 300s).
- block_seconds: bloqueo temporal (ej. 900s).
- El contador se resetea tras autenticación exitosa.

Para producción, configure un `RedisRateLimiter` y registre intentos/fallos en una solución de logs centralizada. Siempre devuelva `Retry-After` a los clientes cuando estén bloqueados.

A
B
C
D
E
F
G
H
I
J
K
L
M
N
O
P
Q
R
S
T
U
