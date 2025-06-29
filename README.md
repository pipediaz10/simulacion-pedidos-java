# simulacion-pedidos-java
Descripción:
------------
Este programa simula cómo se generan y procesan pedidos en una tienda en línea.
Hay varios clientes que crean pedidos (productores) y varios empleados que los procesan (consumidores).
Todo esto pasa al mismo tiempo usando hilos (threads).

Por qué usamos BlockingQueue y AtomicInteger:
---------------------------------------------
- Usamos `BlockingQueue` para que los hilos puedan compartir una cola de pedidos sin errores.
  Así, los productores agregan pedidos y los consumidores los toman sin problemas.

- Usamos `AtomicInteger` para contar cuántos pedidos se procesaron sin que dos hilos se pisen entre sí.

Problemas que evitamos:
------------------------
- No se pierden pedidos ni se procesan dos veces.
- No necesitamos usar bloqueos manuales ni `synchronized`.
- Evitamos errores comunes como bloqueos o condiciones de carrera.
