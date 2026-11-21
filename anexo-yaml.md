# Anexo de configuración YAML

[Volver al índice](README.md)

## YAML

### ✅ 1. YAML usa espacios, NO tabuladores

- Prohibido usar TAB → rompe el fichero.
- Usar siempre 2 o 4 espacios para indentar.

### ✅ 2. La indentación importa

YAML funciona como un árbol.
Si una línea depende de otra, va debajo y con más espacios.

Ejemplo correcto:

~~~yaml
scrape_configs:
  - job_name: 'paris'
    static_configs:
      - targets: ['192.168.1.10:9100']
~~~

### ✅ 3. Los guiones definen listas

Ejemplo de lista de targets:

~~~yaml
- targets: ['localhost:9100']
~~~

### ✅ 4. Cada clave: valor lleva 1 espacio después de los dos puntos

❌ Incorrecto:

~~~yaml
job_name:  'sevilla'
~~~

✔ Correcto:

~~~yaml
job_name: 'sevilla'
~~~

### ✅ 5. Los comentarios empiezan con #

Todo lo que esté después no afecta al contenido.

~~~text
# Esto es un comentario
~~~

### ✅ 6. Validar siempre antes de reiniciar Prometheus

Usar:

~~~text
yamllint archivo.yml
~~~

Si marca error, Prometheus no arrancará.

## 🏆 Regla de oro

👉 Copiar y pegar un bloque que ya funciona y cambiar solo lo necesario.
Así evitan romper la indentación.
