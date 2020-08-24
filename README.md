# Auction-SmartContract
Smart Contract example to explain the methods of design and development for a Smart Contract


## Variables (datos)
```
// Propietario de la subasta
originalOwner: address
newOwner: address

// Información de la subasta
description: string
basePrice: number
secondsToEnd: number
createdTime: number

// Puja más alta
highestBidder: address
highestPrice: number

//  Estado de la subasta
activeContract: boolean (true,false)

// Eventos de estado y resultado
event Status(…)
event Result(…)
```

## Constructor
```
Inicializar las variables (datos) como descripción, precio inicial y duración de la subasta
Activar el contrato
Marcar el instante de creación y propietario-creador del contrato
Emitir evento de creación
```

## Funciones que modifican datos
```
function bid(){ 
    Chequear estado subasta
    Condición (valor_puja > puja_máxima):
           Devolver dinero al ultimo postor
           Actualizar valores de puja más alta
           Emitir evento
    No cumple condición: 
           Emitir evento
           Salir
}
```

```
function checkIfAuctionEnded(){
    Condición (subasta expirada):
            Finalizar la subasta
           Transferir puja más alta al propietario
           Emitir evento
    No cumple condición:
           Salir
}
```

## Funciones de pánico/emergencia
```
function stopAuction(){  
     Condicion: propietario del contrato
              Finalizar subasta
              Devolver el dinero al postor
}
```

## Funciones de consulta
```
function getAuctionInfo(){
     Devolver información de la subasta
}
```
```
function getHighestPrice(){
     Devolver el valor de la puja más alta
}
```

