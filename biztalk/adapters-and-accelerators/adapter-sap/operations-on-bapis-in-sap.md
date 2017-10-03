---
title: Operaciones de BAPI en SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAPI, operations
- BAPIs, operations on
- Business Application Programming Interface
- BAPIs
- BAPI, transactions
- BAPI transactions, limitations on
ms.assetid: 6be26641-e8d3-4e11-8d82-4fdb13076580
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8504dd05c671307085d621c474969a70026d2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-bapis-in-sap"></a>Operaciones de BAPI en SAP
Una interfaz de programación de aplicación de empresariales (BAPI) es un método de un objeto de negocios SAP que puede llamarse mediante un proceso externo. BAPI es transaccional en el sistema SAP.  
  
 El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite BAPI llama en la dirección de salida. Pone de manifiesto BAPI de dos maneras:  
  
-   **Como una RFC**. Puede invocar una BAPI invocando la RFC adecuada.  
  
-   **Como métodos de objetos comerciales**. El adaptador Emerge BAPI como métodos de objetos comerciales como una comodidad para ayudarle a recuperar los metadatos cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].  
  
> [!IMPORTANT]
>  Puede invocar una BAPI en el adaptador como una solicitud de cambio o como un método de un objeto de negocios; pero independientemente de cómo invocar la BAPI en el adaptador, invoca siempre la BAPI en SAP a través de la interfaz RFC.  
  
 El adaptador admite transacciones de BAPI. El modelo de transacción BAPI en SAP permite a los usuarios combinar varias BAPI en una unidad lógica de trabajo (LUW). Un LUW de SAP está formada por todos los pasos implicados en una transacción incluida la actualización de la base de datos.  
  
 Los temas de esta sección explican cómo BAPI aparecen como objetos de negocios y cómo se admiten las transacciones de BAPI (LUWs) por el adaptador.  
 
  
## <a name="bapi-operations-as-business-object-methods"></a>Operaciones de BAPI (como métodos de objetos comerciales)  
 El adaptador de superficies BAPI como métodos de objetos de negocio como una comodidad para ayudarle a recuperar los metadatos cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. El adaptador siempre invoca en el sistema SAP mediante la interfaz de RFC BAPI.  
  
 El adaptador de superficies BAPI por su nombre como operaciones bajo el objeto de negocios adecuada para las operaciones de salida. Objetos de negocios se recopilan por grupo funcional en el nodo de categoría BAPI por el adaptador. (Se puede examinar o buscar BAPI en y objetos de negocios de la **BAPI** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite las siguientes en BAPI:  
  
-   IMPORTACIÓN de parámetros  
  
-   Parámetros de exportación  
  
-   VARIABLES parámetros  
  
-   Parámetros de la tabla  
  
 Para obtener más información sobre las estructuras de mensajes y acciones de SOAP que se usan para BAPI aparecen como métodos de objetos comerciales, vea [esquemas de mensaje para las operaciones de BAPI](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md).  
  
## <a name="bapi-transactions"></a>Transacciones de BAPI  
 Cuando se invoca una BAPI, siempre es parte de un LUW en el sistema SAP. Esto es cierto si se invoca la BAPI como una solicitud de cambio o como un método de un objeto de negocios. RFC SDK trata todos los BAPI enviado a través de la misma conexión de SAP como parte de la misma LUW. Después de llamar a confirmar o revertir la transacción en una conexión, el siguiente BAPI enviada a través de la conexión comienza un nuevo LUW.  
  
 Se llama a BAPI_TRANSACTION_COMMIT o BAPI_TRANSACTION_ROLLBACK para confirmar o revertir la transacción. El adaptador de superficies de estos dos BAPI:  
  
-   En el nodo de base como operaciones de RFC.  
  
-   En cada objeto de negocios.  
  
 Controlar la BAPI en una transacción asegurándose de que todas las envíen a través de la misma conexión de SAP (incluida la llamada para confirmar o revertir la transacción). Para hacer esto:  
  
-   Soluciones de BizTalk mediante el uso de la **ConnectionState** message (propiedad) contexto para asegurarse de que la BAPI en una transacción se envía con la misma conexión. Esta propiedad es obtenida por el adaptador y proporciona un control explícito sobre la conexión usada para enviar un mensaje en una orquestación de BizTalk.  
  
     Para realizar transacciones de BAPI mediante BizTalk Server, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite las siguientes propiedades de contexto de mensaje.  
  
    |Campo|Description|  
    |-----------|-----------------|  
    |OPEN|Abre un canal nuevo para la transacción.|  
    |VOLVER A USAR|Reutilizar un canal existente para la transacción.|  
    |CLOSE|Confirmar la transacción y cierre el canal existente.|  
    |ANULACIÓN|Anular la transacción y cierre el canal existente.|  
  
     Para obtener más información, consulte [ejecutar BAPI transacciones en SAP mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md).  
  
    > [!NOTE]
    >  Asegúrese de establecer el **EnableBizTalkCompatibilityMode**propiedad de enlace al realizar las transacciones que usan el servidor BizTalk Server.  
  
-   Soluciones de modelo de servicio WCF asegurándose de que la BAPI en una transacción se envía con el mismo cliente WCF. Para obtener más información, consulte [invocar BAPI en SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md).  
  
-   WCF canal soluciones de modelos asegurándose de que la BAPI en una transacción se envía a través del mismo canal WCF. Para obtener más información, consulte [desarrollar aplicaciones mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).  
  
### <a name="limitations-on-bapi-transactions"></a>Limitaciones de las transacciones de BAPI  
 Se aplican las siguientes restricciones en las transacciones de BAPI:  
  
-   No es posible crear dos accesos de escritura en la misma instancia dentro de un LUW. Por ejemplo, no puede crear un pedido y actualizarlo en la misma transacción.  
  
-   Al realizar una transacción mediante BAPI [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], todos los mensajes se deben enviar a través de una instancia de host del puerto de envío.  
  
-   Si una instancia se crea, actualiza o elimina mediante el uso de una operación de escritura BAPI, una lectura BAPI no podrá ver los datos más recientes, hasta que se confirma la operación de escritura BAPI.  
  
-   Un cliente externo que invoca un LUW debería llamar a todos lo BAPI que contiene el LUW en la misma conexión de SAP.  
  
> [!IMPORTANT]
>  BAPI que pertenecen a la versión 3.1, llame a COMMIT WORK como parte de su implementación. Esto significa que estos BAPI no puede incluirse con otra BAPI en un LUW (debido a confirmación la transacción). Para obtener más información, consulte la documentación de SAP.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)