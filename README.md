# Performance Testing en K6

Correr prueba con K6

```bash
k6 run name_file.js
```

Resultados HTTP

- Blocked => Esperando un espacio para que nuestra petición sea ejecutada.
- Connection => Estableciendo conexión con el endpoint
- Waiting => Esperando respuesta del endpoint
- Receiving => Tiempo recibiendo toda la data
- Sending => Tiempo que hace desde mandando la data
- Handshaking => Tiempo TLS Handshaking
- Duration => Sendig + Waiting + Receiving
- Failed => Request fallidas

* Iterations => Numero de veces que el script se ejecutó
* Iteration duration => Tiempo de cada iteracion
* VUs Max => Máximos VUs permitidos

Virtual User (VUs)
Simula la actividad de un usuario, le damos un request y lo ejecuta repetidamente.

Stage
Etapa de duración de nuestro test.

```javascript
// crea 10 instancias que simulen 10 usuarios que van a ejecutar
// el test o la petición las veces que puedan durante los 10s.
export const options = {
  vus: 10,
  duration: "10s",
};
// Suspende la ejecución por un tiempo de duración.
sleep(1);
```
