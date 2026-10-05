# Jorge Enríquez Rico - Evidencia 2 AulaPlan-JER 

Añadimos el siguiente codigo en el archivo test_health.py para realizar pruebas unitarias a la ruta /health de nuestra aplicación Flask.
```
from flask import Flask
from src.http.routes_health import health_bp

def test_healt():
    app = create_app(testing=True)
    client = app.test_client()
    response = client.get('/health')
    assert response.status_code == 200
    assert response.get.json()['runtime'] == 'python'
```

Añadimos el siguiente codigo en el archivo dev.py para ejecutar nuestra aplicación Flask en modo de desarrollo.
```
from src.http.app import create_app

app = create_app()

if __name__ == '__main__':
    app.run(debug=True, port=8000)
```