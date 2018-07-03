---
title: Operaciones en BAPI de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI, operations
- BAPIs, operations on
- Business Application Programming Interface
- BAPIs
- BAPI, transactions
- BAPI transactions, limitations on
ms.assetid: 6be26641-e8d3-4e11-8d82-4fdb13076580
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a319626f23b825187d65e01d687be5a1079df53a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993173"
---
# <a name="operations-on-bapis-in-sap"></a>Operaciones en BAPI de SAP
Una interfaz de programación Business Application (BAPI) es un método de un objeto de negocios SAP que se puede llamar a un proceso externo. BAPI es transaccional en el sistema SAP.  
  
 El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite BAPI llama en la dirección de salida. Pone de manifiesto BAPI de dos maneras:  
  
- **Como una RFC**. Puede invocar una BAPI invocando la RFC adecuada.  
  
- **Como los métodos de objetos de negocios**. El adaptador presenta BAPI como métodos de objetos de negocios como una comodidad para ayudarle a recuperar los metadatos cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].  
  
> [!IMPORTANT]
>  Puede invocar una BAPI en el adaptador como una solicitud de cambio o como un método de un objeto comercial; pero, independientemente de cómo invocar la BAPI en el adaptador, siempre invoca la BAPI de SAP a través de la interfaz RFC.  
  
 El adaptador admite transacciones de BAPI. El modelo de transacciones de BAPI de SAP permite a los usuarios combinar varios BAPI en una unidad lógica de trabajo (LUW). Un LUW SAP consta de todos los pasos implicados en una transacción incluida la actualización de la base de datos.  
  
 Los temas de esta sección explican cómo BAPI se expone como objetos de negocios y cómo se admiten las transacciones de BAPI (LUWs) por el adaptador.  
 
  
## <a name="bapi-operations-as-business-object-methods"></a>Operaciones de BAPI (como métodos de objeto de negocios)  
 El adaptador presenta BAPI como métodos de objetos de negocio como una comodidad para ayudarle a recuperar los metadatos cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. El adaptador invoca siempre BAPI en el sistema SAP mediante la interfaz de RFC.  
  
 El adaptador presenta BAPI por su nombre como operaciones en el objeto de negocios adecuados para las operaciones de salida. Objetos de negocios se recopilan por grupo funcional en el nodo de categoría BAPI por el adaptador. (Puede examinar o buscar objetos de negocios y BAPI bajo el **BAPI** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] BAPI admite los siguientes:  
  
- IMPORTACIÓN de parámetros  
  
- Parámetros de exportación  
  
- Parámetros de variación  
  
- Parámetros de la tabla  
  
  Para obtener más información acerca de las estructuras de mensajes y las acciones de SOAP utilizadas para BAPI aparece como métodos de objetos comerciales, vea [esquemas de mensaje para operaciones de BAPI](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md).  
  
## <a name="bapi-transactions"></a>Transacciones de BAPI  
 Cuando se invoca una BAPI, siempre es parte de un LUW en el sistema SAP. Esto es cierto si invocar la BAPI como una solicitud de cambio o como un método de un objeto de negocios. El SDK de RFC trata todos los BAPI enviado a través de la misma conexión de SAP como parte de la misma LUW. Después de llamar a confirmar o revertir la transacción en una conexión, el siguiente BAPI enviada a través de la conexión comienza un nuevo LUW.  
  
 Se llama a BAPI_TRANSACTION_COMMIT o BAPI_TRANSACTION_ROLLBACK para confirmar o revertir la transacción. El adaptador presenta estos dos BAPI:  
  
- En el nodo base como las operaciones de RFC.  
  
- En cada objeto de negocios.  
  
  Controlar las BAPI en una transacción asegurándose de que todos enviarse a través de la misma conexión de SAP (incluida la llamada al confirmar o revertir la transacción). Puede hacerlo en:  
  
- Soluciones de BizTalk mediante el uso de la **ConnectionState** propiedad de contexto para garantizar que las BAPI en una transacción se envían con la misma conexión de mensajes. Esta propiedad es obtenida por el adaptador y le proporciona un control explícito sobre la conexión usada para enviar un mensaje en una orquestación de BizTalk.  
  
   Para realizar transacciones de BAPI mediante BizTalk Server, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite las siguientes propiedades de contexto de mensaje.  
  
  |Campo|Descripción|  
  |-----------|-----------------|  
  |OPEN|Se abre un nuevo canal para la transacción.|  
  |VOLVER A USAR|Reutilizar un canal existente para la transacción.|  
  |CLOSE|Confirmar la transacción y cierra el canal existente.|  
  |ABORT|Anular la transacción y cierra el canal existente.|  
  
   Para obtener más información, consulte [ejecutar transacciones de BAPI de SAP con BizTalk Server](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md).  
  
  > [!NOTE]
  >  Asegúrese de establecer el **EnableBizTalkCompatibilityMode**enlaza la propiedad cuando se realizan transacciones con BizTalk Server.  
  
- Soluciones de modelos de servicio WCF asegurándose de que las BAPI en una transacción se envían con el mismo cliente WCF. Para obtener más información, consulte [invocar BAPI de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md).  
  
- WCF canal soluciones de modelos al garantizar que las BAPI en una transacción se envían a través del mismo canal WCF. Para obtener más información, consulte [desarrollar aplicaciones mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).  
  
### <a name="limitations-on-bapi-transactions"></a>Limitaciones de las transacciones de BAPI  
 Las siguientes restricciones se aplican en transacciones de BAPI:  
  
- No es posible crear dos accesos de escritura en la misma instancia dentro de un LUW. Por ejemplo, no se puede crear un pedido y actualiza en la misma transacción.  
  
- Al realizar una transacción utilizando el BAPI [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], todos los mensajes deben enviarse a través de una instancia de host del puerto de envío.  
  
- Si una instancia se crea, actualiza o elimina mediante el uso de una escritura BAPI, una lectura BAPI no podrá ver los datos más reciente hasta que se confirma la escritura BAPI.  
  
- Un cliente externo que invoca un LUW debe llamar a todas las BAPI que contiene el LUW en la misma conexión de SAP.  
  
> [!IMPORTANT]
>  BAPI que pertenecen a la versión 3.1 llamar a COMMIT WORK como parte de su implementación. Esto significa que estos BAPI no puede incluirse con otra BAPI en un LUW (porque confirmará la transacción). Para obtener más información, consulte la documentación de SAP.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)