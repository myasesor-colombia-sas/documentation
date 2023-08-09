# Authenticacion
Para hacer uso de esta API se debe autenticar en el sistema, el endpoint para autenticarse es el siguiente.

Recordemos que son varios microservicios y el modulo de autenticacion esta en un servidor distinto al del inventario.
# Login


### Descripcion 
En este endpoint podras loguearte en el sistema usando usuario y contraseña.

- *url:* `/api/v1/congusuarios/login/`
- *metodo:* `POST`

### Request
```bash
curl -X 'POST' \
  'http://127.0.0.1:8000/api/v1/congusuarios/login/' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "usua_codigo": "Tu Usuario",
  "usua_clave": "Tu Contraseña"
}'

```

### Response

código de estado será 200 cuando el usuario se registre correctamente, el endpoint retornara el token de acceso y el refresh token.

Este access token tendras que pasarlo como cabezera a las demas mas peticiones que desees hacer ya que es el te valida como un usuario authenticado en en el sistema.
```json
{
  "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNjkxNTk1NjE3LCJpYXQiOjE2OTE1MDkyMTcsImp0aSI6Ijk5MjgxY2MxMTFkNTRiNDk5YWZkN2Y5YzM4ZDdhZWU5IiwidXNlcl9pZCI6Im0xIiwidXN1YV90aXBvIjoiMDAxIn0.ahnmmTzy802JivbevMSv1MbkLdI2oSAIHeUMhJBn1",
  "refresh": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTY5MTU5NTYxNywiaWF0IjoxNjkxNTA5MjE3LCJqdGkiOiI4NmVlMmRhN2M4ZDg0YTA1ODlmMzIzNDM0ZTA4ZGJjMCIsInVzZXJfaWQiOiJtMSIsInVzdWFfdGlwbyI6IjAwMSJ9.nArsXdNXPHSKo3zMGOQCTCL8mgzspDRXZyz4_qAVI",
  "usua_codigo": "m1"
}

```




# Crear movimiento
## Descripción
En este endpoint podras crear las facturas y guardarlas en el sistema.

- *url:* `/api/v1/guardarmovimiento/create/`
- *método:* `POST`

### Request
```bash
curl -X 'POST' \
  'http://127.0.0.1:8001/api/v1/guardarmovimiento/create/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNjkxNTkwNzI4LCJpYXQiOjE2OTE1MDQzMjgsImp0aSI6IjYyZTIxNzU5YzcwMzQzNTI5ZGZkNjIxMGY0NzM5Mzc1IiwidXNlcl9pZCI6Im0xIiwidXN1YV90aXBvIjoiMDAxIn0.YsQXb1JesSIlo3LeNZaCeiwTwhksbnqjeLLCX2A38ZE' \
  -H 'Content-Type: application/json' \
  -d '{
  "head": {
    "movi_bodega": "001",
    "movi_concepto": "001",
    "movi_documento": "227",
    "movi_fecha": "2023-07-01",
    "movi_vrventa": "10",
    "movi_nit": "000000000000",
    "movi_vrcosto": "5.00",
    "movi_estado": "G",
    "movi_ordencompra": "",
    "movi_ordendetrabajo": "",
    "movi_departamento": "",
    "movi_conceptoorigen": null,
    "movi_docanexo": "35240",
    "movi_usuario": "FROMTEST",
    "movi_factor": "0.00",
    "movi_fupdate": "2023-03-18T00:00:00Z",
    "movi_detalle": "",
    "movi_contenedor": "",
    "movi_vriva": "0.00",
    "movi_vrdescuento": "0.00",
    "movi_dtofinanciero": "0.000",
    "movi_vrflete": "0.00",
    "movi_retefte": null,
    "movi_reteiva": null,
    "movi_reteica": null,
    "movi_timbre": null,
    "movi_otros": null,
    "movi_trm": null,
    "movi_fdocanexo": null,
    "movi_vencimiento": null,
    "movi_vendedor": null,
    "movi_pais": null,
    "movi_zona": null,
    "movi_subzona": null,
    "movi_tipo": null,
    "movi_tpcuenta": "004"
  },
  "body": [
    {
      "kard_ccosto": "001",
      "kard_bodega": "001",
      "kard_concepto": "001",
      "kard_documento": "227",
      "kard_caja": null,
      "kard_item": 2,
      "kard_articulo": "001001",
      "kard_codigobarra": null,
      "kard_qtypedida": 0,
      "kard_cantidad": 12,
      "kard_valorunitario": 50000,
      "kard_valorunitarioniif": 0,
      "kard_costopromedio": 0,
      "kard_valorventa": 1245,
      "kard_valorpromocion": 0,
      "kard_vrarancel": 0,
      "kard_vrantidumping": 0,
      "kard_saldo": 0,
      "kard_clase": "E",
      "kard_estado": "G",
      "kard_categoria": null,
      "kard_bitacora": "",
      "kard_pdescuento": 0,
      "kard_pdtofciero": 0,
      "kard_descargamvto": "S",
      "kard_valordolar": 0,
      "kard_valorflete": 0,
      "kard_iva": 19,
      "kard_codigoiva": "02",
      "kard_ico": null,
      "kard_tipodescuento": null,
      "kard_fecha": "2023-03-18",
      "kard_proveedor": "000000000000",
      "kard_lote": null,
      "kard_incremento": null,
      "kard_itemparent": null,
      "kard_itemrelacion": null,
      "kard_fechaturno": null,
      "kard_pluparent": null,
      "kard_lprecios": null,
      "kard_impubolsa": null,
      "kard_undmenudeo": null,
      "kard_nitrelacion": null,
      "kard_fcreate": "2023-03-18T00:00:00Z",
      "kard_usuario": "UPLOAD",
      "kard_usrupdate": null,
      "kard_fupdate": null,
      "kard_rowid": 124991
    },
    {
      "kard_ccosto": "001",
      "kard_bodega": "001",
      "kard_concepto": "001",
      "kard_documento": "227",
      "kard_caja": null,
      "kard_item": 3,
      "kard_articulo": "002007",
      "kard_codigobarra": null,
      "kard_qtypedida": 0,
      "kard_cantidad": 54,
      "kard_valorunitario": 6000,
      "kard_valorunitarioniif": 0,
      "kard_costopromedio": 0,
      "kard_valorventa": 150,
      "kard_valorpromocion": 0,
      "kard_vrarancel": 0,
      "kard_vrantidumping": 0,
      "kard_saldo": 0,
      "kard_clase": "E",
      "kard_estado": "G",
      "kard_categoria": null,
      "kard_bitacora": "",
      "kard_pdescuento": 0,
      "kard_pdtofciero": 0,
      "kard_descargamvto": "S",
      "kard_valordolar": 0,
      "kard_valorflete": 0,
      "kard_iva": 5,
      "kard_codigoiva": "04",
      "kard_ico": null,
      "kard_tipodescuento": null,
      "kard_fecha": "2023-03-18",
      "kard_proveedor": "000000000000",
      "kard_lote": null,
      "kard_incremento": null,
      "kard_itemparent": null,
      "kard_itemrelacion": null,
      "kard_fechaturno": null,
      "kard_pluparent": null,
      "kard_lprecios": null,
      "kard_impubolsa": null,
      "kard_undmenudeo": null,
      "kard_nitrelacion": null,
      "kard_fcreate": "2023-03-18T00:00:00Z",
      "kard_usuario": "UPLOAD",
      "kard_usrupdate": null,
      "kard_fupdate": null,
      "kard_rowid": 124992
    }
  ]
}'
```
### Response

código de estado será 200 cuando el documento se cree corectamente

```json
{"status": "created"}

```
