## JsonSchema

- https://jsonschema.net/

### Como utilizar
- Inserir um exemplo de corpo da requisição do JsonSchema, que vai gerar um script para validação desse corpo. 

### Exemplo de script de teste:

```
const schema = {
    "$id": "http://example.com/example.json",
    "title": "Root Schema",
    "type": "object",
    "default": {},
    "required": [
        "data",
        "errors"
    ],
    "properties": {
        "data": {
            "title": "The data Schema",
            "type": "object",
            "default": {},
            "required": [
                "id",
                "localDeDestino",
                "dataPartida",
                "dataRetorno",
                "acompanhante",
                "regiao"
            ],
            "properties": {
                "id": {
                    "title": "The id Schema",
                    "type": "integer",
                    "default": 0,
                    "examples": [
                        1
                    ]
                },
                "localDeDestino": {
                    "title": "The localDeDestino Schema",
                    "type": "string",
                    "default": "",
                    "examples": [
                        "Teste"
                    ]
                },
                "dataPartida": {
                    "title": "The dataPartida Schema",
                    "type": "string",
                    "default": "",
                    "examples": [
                        "2025-01-28"
                    ]
                },
                "dataRetorno": {
                    "title": "The dataRetorno Schema",
                    "type": "string",
                    "default": "",
                    "examples": [
                        "2025-03-03"
                    ]
                },
                "acompanhante": {
                    "title": "The acompanhante Schema",
                    "type": "string",
                    "default": "",
                    "examples": [
                        "Acompanhante"
                    ]
                },
                "regiao": {
                    "title": "The regiao Schema",
                    "type": "string",
                    "default": "",
                    "examples": [
                        "Norte"
                    ]
                }
            },
            "examples": [{
                "id": 1,
                "localDeDestino": "Teste",
                "dataPartida": "2025-01-28",
                "dataRetorno": "2025-03-03",
                "acompanhante": "Acompanhante",
                "regiao": "Norte"
            }]
        },
        "errors": {
            "title": "The errors Schema",
            "type": "array",
            "default": [],
            "items": {},
            "examples": [
                []
            ]
        }
    },
    "examples": [{
        "data": {
            "id": 1,
            "localDeDestino": "Teste",
            "dataPartida": "2025-01-28",
            "dataRetorno": "2025-03-03",
            "acompanhante": "Acompanhante",
            "regiao": "Norte"
        },
        "errors": []
    }]
}

pm.test("Validar a estrutura do corpo da resposta", function ( ){
    pm.response.to.have.jsonSchema(schema);
});
```

Dica: No JSON Schema Tool, selecionar a opção "Draft 7" e desmarcar a opção "$schema" no combobox "KeyWords". 