---
title: Functoids de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77bc9390-cdb5-42ff-8b28-6265c51c79fc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5c0b1be12176653bba2414e32bdefbd83e9083
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013837"
---
# <a name="database-functoids"></a>Functoids de base de datos
**Base de datos** functoids extraer datos de una base de datos para su uso en un mensaje de instancia de salida. 

## <a name="overview"></a>Información general
La siguiente es una lista de los **base de datos** functoids y cómo puede usar:  

- **Búsqueda de la base de datos.** Use la **búsqueda de la base de datos** functoid para extraer información de una base de datos y almacenarla como un conjunto de registros de Microsoft ActiveX Data Objects .NET (ADO.NET). Este functoid requiere cuatro parámetros de entrada en el orden siguiente:  

  -   Un valor de búsqueda  

  -   Una cadena de conexión de base de datos  

  -   Un nombre de tabla  

  -   Un nombre de columna para el valor de búsqueda.  

- **Devolución de error.** Use la **devolución de Error** functoid para capturar la información de error, como errores de conexión de base de datos, que se producen durante el tiempo de ejecución. Este functoid requiere un parámetro de entrada: un vínculo desde el **búsqueda de la base de datos** functoid.  

- **Formato de mensaje.** Devuelve una cadena formateada y localizada utilizando sustitución de argumentos y, potencialmente, referencias cruzadas a valores e Id.  

- **Obtener el identificador de aplicación.** Recupera un identificador de un objeto de aplicación.  

- **Obtener valor de aplicación.** Recupera un valor de aplicación.  

- **Obtener Id. común.** Recupera un identificador de un objeto común.  

- **Obtener valor común.** Recupera un valor común.  

- **Quitar Id. de aplicación.** Quita un valor de aplicación.  

- **Establecer Id. común.** Establece y devuelve un identificador para un objeto común.  

- **Extractor de valor.** Use la **Extractor de valor** functoid para extraer datos de la columna especificada en un conjunto de registros devuelto por la **búsqueda de la base de datos** functoid. Este functoid requiere dos parámetros de entrada: un vínculo a la **búsqueda de la base de datos** functoid y un nombre de columna.  

  Siete de los **base de datos** functoids, **formatear mensaje, obtener Id. de aplicación**, **obtener valor de aplicación**, **obtener Id. común**, **Obtener valor común**, **quitar Id. de aplicación**, y **establecer Id. común**— son **CrossReferencing** functoids. Estos functoids trasladan los Id. y valores de un mensaje de entrada a los Id. y valores que se necesitan en el mensaje de salida. Para obtener más información, consulte **referencia a Functoids de base de datos** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 

## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa algunos de los **base de datos** functoids. Imagine un gran fabricante de comercios al por menor, con tiendas distribuidas por una extensa área geográfica. Para realizar un seguimiento de los almacenes, oficina central asigna a cada almacén de un código único llamado un **StoreID**. Además, la oficina central asocia la siguiente información con cada **StoreID**:  

- StoreName  

- StoreAddress  

- City  

- PostalCode  

- StorePhoneNumber  

- StoreManager  

  Esta información se almacena en una base de datos y se distribuye a los socios comerciales periódicamente. Para el fabricante, todas las compras las realiza la oficina central, no las tiendas. Cuando la oficina central envía un pedido a los socios comerciales, es habitual que varias tiendas reciban mercancía encargada mediante el pedido único. En lugar de enviar información de nombre y la dirección de cada tienda que tiene que recibir mercancía, oficina central envía simplemente el **StoreID**. Para insertar la información de nombre y la dirección en la notificación previa de envío, el socio comercial utiliza el **base de datos** functoids para insertar automáticamente esta información en el mensaje de instancia de salida. En la siguiente ilustración se muestra cómo puede implementar un socio comercial la sustitución del StoreID en una asignación.  

  ![Functoids de base de datos diferente que muestra de mapa. ] (../core/media/origdbfunctoids.gif "origdbfunctoids")  

  En la ilustración, el esquema de origen representa un pedido entrante; el esquema de destino representa una notificación previa de envío. El **búsqueda de la base de datos** functoid busca el registro adecuado de la tabla de base de datos adecuada. El **Extractor de valor** functoids extraen la columna apropiada del registro de búsqueda. El **devolución de Error** functoid genera una cadena que contiene información de error si hay errores (por ejemplo, errores de conexión) en tiempo de ejecución.  

  En el ejemplo anterior, se toma el primer parámetro de entrada de la **StoreID** campo de la entrada de pedido de compra y los restantes tres parámetros de entrada son constantes configuradas en el **configurar \< Functoid\> Functoid** cuadro de diálogo para la **búsqueda de la base de datos** functoid. Es posible crear vínculos desde el esquema de origen para suministrar valores a los cuatro parámetros de entrada.  

> [!NOTE]
>  * No se puede usar algunos tipos de datos de Microsoft SQL Server, como **texto**, **ntext**, y **imagen**, como valores de búsqueda para el **búsqueda de la base de datos** functoid. El functoid requiere tipos de datos que puedan representarse como una cadena de texto.  
>
>  * Si hay más de un registro que coincida con los parámetros de entrada de la **búsqueda de la base de datos** functoid, la **Extractor de valor** functoid extrae datos solamente del primer registro.  
>
>  * Utilice autenticación de NT en las cadenas de conexión para proteger las contraseñas mediante cifrado.  

## <a name="available-functoids"></a>Functoids disponibles  
 El **base de datos** functoids son: 

* Búsqueda en base de datos
* Devolución de error
* Formatear mensaje
* Obtener Id. de aplicación
* Obtener valor de aplicación
* Obtener Id. común
* Obtener valor común
* Quitar Id. de aplicación
* Establecer Id. común
* Extractor de valor

Para obtener más detalles sobre estas funciones, vea el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

## <a name="see-also"></a>Vea también  
- [Cómo agregar Functoids básicos a una asignación](../core/how-to-add-basic-functoids-to-a-map.md)   
- **Referencia a Functoids de base de datos** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
