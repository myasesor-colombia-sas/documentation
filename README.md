# Authenticacion
Para hacer uso de esta API se debe autenticar el endpoint para autenticarse es el siguiente.

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

```json
{
  "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNjkxNTk1NjE3LCJpYXQiOjE2OTE1MDkyMTcsImp0aSI6Ijk5MjgxY2MxMTFkNTRiNDk5YWZkN2Y5YzM4ZDdhZWU5IiwidXNlcl9pZCI6Im0xIiwidXN1YV90aXBvIjoiMDAxIn0.ahnmmTzy802JivbevMSv1MbkLdI2oSAIHeUMhJBn1",
  "refresh": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTY5MTU5NTYxNywiaWF0IjoxNjkxNTA5MjE3LCJqdGkiOiI4NmVlMmRhN2M4ZDg0YTA1ODlmMzIzNDM0ZTA4ZGJjMCIsInVzZXJfaWQiOiJtMSIsInVzdWFfdGlwbyI6IjAwMSJ9.nArsXdNXPHSKo3zMGOQCTCL8mgzspDRXZyz4_qAVI",
  "usua_codigo": "m1"
}

```




# Crear movimiento
## Descripción

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
      "kard_item": 1,
      "kard_articulo": "002001",
      "kard_codigobarra": null,
      "kard_qtypedida": 0,
      "kard_cantidad": 15,
      "kard_valorunitario": 5658,
      "kard_valorunitarioniif": 0,
      "kard_costopromedio": 0,
      "kard_valorventa": 10,
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
      "kard_iva": 0,
      "kard_codigoiva": "01",
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
      "kard_rowid": 124990
    },
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
    },
    {
      "kard_ccosto": "001",
      "kard_bodega": "001",
      "kard_concepto": "001",
      "kard_documento": "227",
      "kard_caja": null,
      "kard_item": 4,
      "kard_articulo": "002009",
      "kard_codigobarra": null,
      "kard_qtypedida": 0,
      "kard_cantidad": 15,
      "kard_valorunitario": 5658,
      "kard_valorunitarioniif": 0,
      "kard_costopromedio": 0,
      "kard_valorventa": 10,
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
      "kard_iva": 0,
      "kard_codigoiva": "01",
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
      "kard_rowid": 124993
    },
    {
      "kard_ccosto": "001",
      "kard_bodega": "001",
      "kard_concepto": "001",
      "kard_documento": "227",
      "kard_caja": null,
      "kard_item": 5,
      "kard_articulo": "002001",
      "kard_codigobarra": null,
      "kard_qtypedida": 0,
      "kard_cantidad": 15,
      "kard_valorunitario": 5658,
      "kard_valorunitarioniif": 0,
      "kard_costopromedio": 0,
      "kard_valorventa": 10,
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
      "kard_iva": 0,
      "kard_codigoiva": "01",
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
      "kard_rowid": 124994
    }
  ]
}'
```
### Response

código de estado será 200 cuando el documento se cree corectamente

```json
{"status": "created"}

```

# Listar todos los movimientos
Descripción

- *url:* `/api/v1/guardarmovimiento/list/`
- *método:* `GET`

## Request

```bash
curl -X 'GET' \
  'http://127.0.0.1:8001/api/v1/guardarmovimiento/list/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNjkxNTkwNzI4LCJpYXQiOjE2OTE1MDQzMjgsImp0aSI6IjYyZTIxNzU5YzcwMzQzNTI5ZGZkNjIxMGY0NzM5Mzc1IiwidXNlcl9pZCI6Im0xIiwidXN1YV90aXBvIjoiMDAxIn0.YsQXb1JesSIlo3LeNZaCeiwTwhksbnqjeLLCX2A38ZE'

```


## Response

código de estado será 200 cuando el listado se realice correctamente

```json
{
  "count": 4295,
  "next": "http://127.0.0.1:8001/api/v1/guardarmovimiento/list/?page=2",
  "previous": null,
  "results": [  
    {
      "head": {
        "movi_bodega": "001",
        "movi_concepto": "001",
        "movi_documento": "106",
        "movi_fecha": "2016-03-01",
        "movi_vrventa": 730208,
        "movi_nit": "000830018214",
        "movi_vrcosto": 730208,
        "movi_estado": "I",
        "movi_ordencompra": "FV001210394 ",
        "movi_ordendetrabajo": "",
        "movi_departamento": "",
        "movi_conceptoorigen": null,
        "movi_docanexo": "FV001210394 ",
        "movi_usuario": "SUGEIS FUENTES JINETE",
        "movi_factor": 0,
        "movi_fupdate": "2016-03-01T17:35:52Z",
        "movi_detalle": "",
        "movi_contenedor": "",
        "movi_vriva": 0,
        "movi_vrdescuento": 0,
        "movi_dtofinanciero": 0,
        "movi_vrflete": 0,
        "movi_retefte": 0,
        "movi_reteiva": 0,
        "movi_reteica": 0,
        "movi_timbre": 0,
        "movi_otros": 0,
        "movi_trm": 0,
        "movi_fdocanexo": "2016-03-01",
        "movi_vencimiento": "2016-03-01",
        "movi_vendedor": null,
        "movi_pais": null,
        "movi_zona": null,
        "movi_subzona": null,
        "movi_tipo": null,
        "movi_cajero": null,
        "movi_caja": null,
        "movi_pedido": "",
        "movi_transaccion": "",
        "movi_notadv": null,
        "movi_remision": "",
        "movi_lista": "",
        "movi_aiu": 0,
        "movi_imprevisto": 0,
        "movi_utilidad": 0,
        "movi_admon": 0,
        "movi_tpcuenta": null,
        "movi_ecomercio": null,
        "movi_prefijodian": null,
        "movi_valor01": 0,
        "movi_valor02": null,
        "movi_valor03": null,
        "movi_retecree": 0,
        "movi_vranticipo": 0,
        "movi_usrupdate": null
      },
      "body": [
        {
          "kard_ccosto": "001",
          "kard_bodega": "001",
          "kard_concepto": "001",
          "kard_documento": "106",
          "kard_caja": null,
          "kard_item": 1,
          "kard_articulo": "001028",
          "kard_codigobarra": "001028",
          "kard_qtypedida": 0,
          "kard_cantidad": 1,
          "kard_valorunitario": 730208,
          "kard_valorunitarioniif": 730208,
          "kard_costopromedio": 73020880,
          "kard_valorventa": 73020880,
          "kard_valorpromocion": 0,
          "kard_vrarancel": 0,
          "kard_vrantidumping": 0,
          "kard_saldo": 1,
          "kard_clase": "E",
          "kard_estado": "G",
          "kard_categoria": "001",
          "kard_bitacora": null,
          "kard_pdescuento": 0,
          "kard_pdtofciero": 0,
          "kard_descargamvto": "S",
          "kard_valordolar": 0,
          "kard_valorflete": 0,
          "kard_iva": 0,
          "kard_codigoiva": null,
          "kard_ico": 0,
          "kard_tipodescuento": null,
          "kard_fecha": "2016-03-01",
          "kard_proveedor": "000830018214",
          "kard_lote": "",
          "kard_incremento": 0,
          "kard_itemparent": null,
          "kard_itemrelacion": 0,
          "kard_fechaturno": null,
          "kard_pluparent": null,
          "kard_lprecios": null,
          "kard_impubolsa": 0,
          "kard_undmenudeo": 0,
          "kard_nitrelacion": null,
          "kard_fcreate": "2016-03-01T17:33:54Z",
          "kard_usuario": "SUGEIS FUENTES JINETE",
          "kard_usrupdate": "SUGEIS FUENTES JINETE",
          "kard_fupdate": "2016-03-01T17:35:53Z",
          "kard_rowid": 826
        }
      ]
    },
    {
      "head": {
        "movi_bodega": "001",
        "movi_concepto": "001",
        "movi_documento": "107",
        "movi_fecha": "2016-05-03",
        "movi_vrventa": 1240000,
        "movi_nit": "000830018214",
        "movi_vrcosto": 1240000,
        "movi_estado": "G",
        "movi_ordencompra": "FV-001225607",
        "movi_ordendetrabajo": "",
        "movi_departamento": "",
        "movi_conceptoorigen": null,
        "movi_docanexo": "FV-001225607",
        "movi_usuario": "ADMINISTRADOR",
        "movi_factor": 0,
        "movi_fupdate": "2016-05-13T15:05:09Z",
        "movi_detalle": "",
        "movi_contenedor": "",
        "movi_vriva": 0,
        "movi_vrdescuento": 0,
        "movi_dtofinanciero": 0,
        "movi_vrflete": 0,
        "movi_retefte": 0,
        "movi_reteiva": 0,
        "movi_reteica": 0,
        "movi_timbre": 0,
        "movi_otros": 0,
        "movi_trm": 0,
        "movi_fdocanexo": "2016-05-03",
        "movi_vencimiento": "2016-05-03",
        "movi_vendedor": null,
        "movi_pais": null,
        "movi_zona": null,
        "movi_subzona": null,
        "movi_tipo": null,
        "movi_cajero": null,
        "movi_caja": null,
        "movi_pedido": "",
        "movi_transaccion": "",
        "movi_notadv": null,
        "movi_remision": "",
        "movi_lista": "",
        "movi_aiu": 0,
        "movi_imprevisto": 0,
        "movi_utilidad": 0,
        "movi_admon": 0,
        "movi_tpcuenta": null,
        "movi_ecomercio": null,
        "movi_prefijodian": null,
        "movi_valor01": 0,
        "movi_valor02": null,
        "movi_valor03": null,
        "movi_retecree": 0,
        "movi_vranticipo": 0,
        "movi_usrupdate": null
      },
      "body": [
        {
          "kard_ccosto": "001",
          "kard_bodega": "001",
          "kard_concepto": "001",
          "kard_documento": "107",
          "kard_caja": null,
          "kard_item": 1,
          "kard_articulo": "001020",
          "kard_codigobarra": "001020",
          "kard_qtypedida": 0,
          "kard_cantidad": 2,
          "kard_valorunitario": 620000,
          "kard_valorunitarioniif": 620000,
          "kard_costopromedio": 0,
          "kard_valorventa": 775000,
          "kard_valorpromocion": 0,
          "kard_vrarancel": 0,
          "kard_vrantidumping": 0,
          "kard_saldo": 0,
          "kard_clase": "E",
          "kard_estado": "G",
          "kard_categoria": "001",
          "kard_bitacora": null,
          "kard_pdescuento": 0,
          "kard_pdtofciero": 0,
          "kard_descargamvto": "",
          "kard_valordolar": 0,
          "kard_valorflete": 0,
          "kard_iva": 0,
          "kard_codigoiva": null,
          "kard_ico": 0,
          "kard_tipodescuento": null,
          "kard_fecha": "2016-05-03",
          "kard_proveedor": "000830018214",
          "kard_lote": "",
          "kard_incremento": 0,
          "kard_itemparent": null,
          "kard_itemrelacion": 0,
          "kard_fechaturno": null,
          "kard_pluparent": null,
          "kard_lprecios": null,
          "kard_impubolsa": 0,
          "kard_undmenudeo": 0,
          "kard_nitrelacion": null,
          "kard_fcreate": "2016-05-13T15:05:09Z",
          "kard_usuario": "ADMINISTRADOR",
          "kard_usrupdate": "ADMINISTRADOR",
          "kard_fupdate": "2016-05-13T15:05:09Z",
          "kard_rowid": 877
        }
      ]
    }
  ]
}

```