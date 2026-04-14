
Comando para terminar una tarea por un puerto que no esta en uso NETBEANS error desarrolladores

1 - Mostrar Puertos y PID

netstat -ano

2 - Buscar puertos

netstat -ano | findstr:0000

3 - Finalizar tarea con puerto que no esta en uso.

taskkill /PID XXXXX /F