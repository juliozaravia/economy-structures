# Endpoints del Back Office
## 1. Categories.
**GET**. `localhost:3001/api/bo/category`

    {
        "id": 1,
        "name": "Sports",
        "createdAt": "2020-10-05T06:17:16.178Z",
        "updatedAt": "2021-11-22T13:12:12.113Z"
    },

**POST**. `localhost:3001/api/bo/category/add`

```json
{
    "name": "Soy otra categoria"
}
```

**PUT**. `localhost:3001/api/bo/category/edit`

```json
{
    "id": 3,
    "name": "este es el nuevo nombre"
}
```

## 2. Services.
**GET**. `localhost:3001/api/bo/service`

```json
{
        "id": 2,
        "name": "Auto Loan Account",
        "price": "96930.68",
        "description": "Credit Card Account",
        "img_url": "Money Market Account",
        "categories": [
            {
                "id": 1,
                "name": "Sports"
            },
            {
                "id": 2,
                "name": "Home"
            },
            {
                "id": 3,
                "name": "Tools"
            }
        ]
    }
```

**POST**. `localhost:3001/api/bo/service/add`

```json
{
    "name": "Sellado de documentos",
    "price": "1000.50",
    "description": "Lorem ipsum dolor sit amet",
    "img_url": "aca_va_una_url",
    "categories": [
        1,
        2
    ]
}
```

**PUT**. `localhost:3001/api/bo/service/edit`

```json
{
    "service_id": 1,
    "name": "nuevo nombre",
	"price": "1000.50",
    "description": "Lorem ipsum dolor sit amet",
    "img_url": "aca_va_una_url",
    "modifiedCategories": {
        "oldCategories": [
            1,
            2,
            3
        ],
        "newCategories": [
            1,
            2
        ]
    }
}
```
