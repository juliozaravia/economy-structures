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

## 3. Orders.
**GET**. `localhost:3001/api/bo/order`

**Sin editar >**

```json
{
        "id": 2,
        "status": "pending",
        "priority": false,
        "start_date": null,
        "end_date": null,
        "assigned_user_id": null,
        "assigned_user": {},
        "invoice_id": 2,
        "invoice": {
            "id": 2,
            "payment_method": "mercadopago",
            "amount": "100.00",
            "status": "done",
            "services": [
                {
                    "id": 2,
                    "name": "Auto Loan Account",
                    "price": "96930.68"
                },
                {
                    "id": 3,
                    "name": "Personal Loan Account",
                    "price": "25173.89"
                },
                {
                    "id": 1,
                    "name": "Otro servicio",
                    "price": "53475.21"
                }
            ]
        }
}
```

**Editado >**

```json
{
        "id": 2,
        "status": "confirmed",
        "priority": true,
        "start_date": "2021-05-27T10:23:16.667Z",
        "end_date": "2021-05-30T10:23:16.667Z",
        "assigned_user_id": 2,
        "assigned_user": {
            "id": 2,
            "name": "Ashleigh Cruickshank",
            "phone": "1-364-342-8043 x1310",
            "email": "Guido_Fay@hotmail.com"
        },
        "invoice_id": 2,
        "invoice": {
            "id": 2,
            "payment_method": "mercadopago",
            "amount": "100.00",
            "status": "done",
            "services": [
                {
                    "id": 2,
                    "name": "Auto Loan Account",
                    "price": "96930.68"
                },
                {
                    "id": 3,
                    "name": "Personal Loan Account",
                    "price": "25173.89"
                },
                {
                    "id": 1,
                    "name": "Otro servicio",
                    "price": "53475.21"
                }
            ]
        }
}
```

**POST**. `localhost:3001/api/bo/order/add`

```json
{
    "invoice_id": 4,
    "status": "pending",
    "priority": true,
    "assigned_user_id": 3
}
```

**PUT**. `localhost:3001/api/bo/order/edit`

```json
{
    "id": 2,
    "assigned_user_id": 2,
    "status": "nuevo",
    "start_date": "2021-05-27 05:23:16.667-05",
    "end_date": "2021-05-30 05:23:16.667-05",
    "priority": true
}
```
