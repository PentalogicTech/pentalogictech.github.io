
# study/getstudyurl()

>*Método que recibe el DNI + AN y devuelve la URL del estudio*


**Método:** *GET*


**URL:** *[https://pacscentral.pentalogic.ar/api/study/getstudyurl.php](https://pacscentral.pentalogic.ar/api/study/getstudyurl.php)*


**Authorization Token:** *(solicitar)*


**Parámetros:** 
- pat_id - integer
- accession_no - string


**Responses:**

- **200 OK** - Response Schema: application/json
```markdown
result: Array of objects
  	Array [
   	  url: string
        ]
```	
- **200 OK** - Response Schema: application/json
```markdown
   result: object	
	message: string
```	
- **400 Bad Request** - Response Schema: application/json
```markdown
   resultError: object	
	message: string
```
- **401 Unauthorized token** - Response Schema: application/json
```markdown
   resultError: object	
	message: string
```
<br>
<br>
<br>

# study/getstudylist()

>*Método que recibe el DNI + Fecha Desde + Fecha Hasta y devuelve el listado de estudios*


**Método:** *GET*


**URL:** *[https://pacscentral.pentalogic.ar/api/study/getstudylist.php](https://pacscentral.pentalogic.ar/api/study/getstudylist.php)*


**Authorization Token:** *37061723-12bb-4766-a1df-d12c2e1c0241*


**Parámetros:** 
- pat_id - integer
- fecha_desde - date
- fecha_hasta - date

**Responses:**

- **200 OK** - Response Schema: application/json
```markdown
result: Array of objects
  	Array [
   	  pat_id: integer,
			study_datetime: datetime,
			accession_no: string,
			study_desc: string,
			mods_in_study: string,
			url: string
        ]
```	
- **200 OK** - Response Schema: application/json
```markdown
   result: object	
	message: string
```	
- **400 Bad Request** - Response Schema: application/json
```markdown
   resultError: object	
	message: string
```
- **401 Unauthorized token** - Response Schema: application/json
```markdown
   resultError: object	
	message: string
```
<br>
<br>
<br>

# worklist/create()

>*Método que recibe datos de un ingreso de paciente e inserta en la cola de envío al servidor de worklist*


**Método:** *POST*


**URL:** *[https://pacscentral.pentalogic.ar/api/worklist/create.php](https://pacscentral.pentalogic.ar/api/worklist/create.php)*


**Authorization Token:** *(solicitar)*


**Request:**

- Body Schema: application/json
```markdown
object
	accion: string ['NW','CA']
	accessionnumber: string
	modalidad: string ['CR','MR','CT','US','DX','MG','NM','NN']
	estudio: string
	apellido: string
	nombre: string
	dni: integer
	fechanac: integer ['YYYYMMDD']
	sexo: string ['M','F']
	aetitle: string
```


**Responses:**

- **200 OK** - Response Schema: application/json
```markdown
   result: object	
	message: string
```	
- **503 Service Unavailable** - Response Schema: application/json
```markdown
   resultError: object	
	message: string
```
- **400 Bad Request** - Response Schema: application/json
```markdown
   resultError: object	
	message: string
```
- **401 Unauthorized token** - Response Schema: application/json
```markdown
   resultError: object	
	message: string
```
<br>
<br>
<br>

# worklist/list()

>*Método que permite listar los registros que se encuentran en la cola de envío a worklist, en estado pendiente*


**Método:** *GET*


**URL:** *[https://pacscentral.pentalogic.ar/api/worklist/list.php](https://pacscentral.pentalogic.ar/api/worklist/list.php)*


**Authorization Token:** *(solicitar)*


**Responses:**

- **200 OK** - Response Schema: application/json
```markdown
result: Array of objects
  	Array [
   	  accion: string ['NW','CA']
	  accessionnumber: string
	  modalidad: string ['CR','MR','CT','US','DX','MG','NM','NN']
	  estudio: string
	  apellido: string
	  nombre: string
	  dni: integer
	  fechanac: integer ['YYYYMMDD']
	  sexo: string ['M','F']
	  aetitle: string
        ]
```	
- **200 OK** - Response Schema: application/json
```markdown
   result: object	
	message: string
```	
- **401 Unauthorized token** - Response Schema: application/json
```markdown
   resultError: object	
	message: string
```
<br>
<br>
<br>
