---
title: Datos almacenados para informes de estado EDI | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec66e4d7-2694-499f-a60c-2f80fe643e12
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90d130d3151f16892e66e02eed834d124b1a2c1e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023234"
---
# <a name="data-stored-for-edi-status-reports"></a>Datos almacenados para informes de estado de EDI
Existen dos niveles de informes están disponibles en los informes de estado EDI: el primero tiene lugar si la **activar informes** propiedad está seleccionada para un acuerdo y el segundo si el **informes de carga y conjunto de transacciones de Store** propiedad está seleccionada para un acuerdo. Estas propiedades están disponibles en el **propiedades generales** página de la **General** pestaña en el **las propiedades del acuerdo** cuadro de diálogo.  
  
## <a name="data-stored-if-edi-reporting-is-activated"></a>Datos almacenados si están activados los informes de EDI  
 Si el **activar informes** propiedad está seleccionada para un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] guardará un registro de todos los intercambios enviados o recibidos, las confirmaciones técnicas y las confirmaciones funcionales.  
  
 En el caso de intercambios recibidos, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacena los datos siguientes:  
  
- Un registro de todos los intercambios recibidos. Constituye la primera información que se muestra en la interfaz de usuario de informes de estado de EDI.  
  
- Un registro de todos los conjuntos de transacciones incluidos en el intercambio. No incluye todos los detalles almacenados cuando el almacenamiento de conjuntos de transacciones está habilitado.  
  
- Un registro de todas las confirmaciones técnicas presentes en el intercambio recibido  
  
- Un registro de todas las confirmaciones funcionales presentes en el intercambio recibido  
  
  > [!NOTE]
  >  Si un intercambio tiene varios grupos funcionales, se almacenarán varias confirmaciones funcionales en la interfaz de usuario de informes de estado. Sin embargo, si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe confirmaciones funcionales duplicadas para un grupo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo almacenará la última en esa interfaz.  
  
- Si es necesario generar una confirmación técnica para el intercambio recibido  
  
- Si es necesario generar confirmaciones funcionales para los conjuntos de transacciones recibidos  
  
  En el caso de intercambios enviados, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacena los datos siguientes:  
  
- Un registro del intercambio enviado  
  
- Un registro de todos los conjuntos de transacciones incluidos en el intercambio  
  
- Un registro de todas las confirmaciones técnicas presentes en el intercambio enviado  
  
- Un registro de todas las confirmaciones funcionales presentes en el intercambio enviado  
  
  La interfaz de usuario de estado de EDI correlaciona estos registros para mostrar la información completa. Por ejemplo, si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un intercambio y es necesario enviar una confirmación técnica y una funcional al remitente del mensaje original, puede encontrar fácilmente esta información en la interfaz de usuario de informes de estado.  
  
## <a name="data-stored-if-transaction-set-storage-is-enabled"></a>Datos almacenados si el almacenamiento de conjuntos de transacciones está habilitado  
 Si el **Store carga de mensaje para el informe** propiedad está seleccionada para un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacenará detalles de todos los conjuntos de transacciones se encuentra en un intercambio enviado o recibido. Este nivel de informes de estado implementa todos los informes del primer nivel realizados si los informes de EDI están activados, más información específica de conjuntos de transacciones. Canalización de recepción de EDI y enviar canalización realiza entradas en la base de datos BAM para cada conjunto de grupo o la transacción entrante y saliente (mientras que el "**informes de carga de mensaje de Store** propiedad está seleccionada). Si se rechaza el intercambio, no se realiza ninguna entrada.  
  
 En el caso de intercambios enviados o recibidos, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacena los datos siguientes:  
  
-   El contenido del conjunto de transacciones. En la interfaz de usuario de informes de estado, puede analizar los conjuntos de transacciones incluidos en un intercambio y, después, ver el contenido del conjunto de transacciones real.  
  
-   Información más detallada acerca de un conjunto de transacciones, incluida la siguiente:  
  
|||  
|-|-|  
|Información|Campo o Valor|  
|ApplicationSender|(GS02 o \<UNG2.1(UNG2.2)\>|  
|ApplicationReceiver|GS03 o \<ung3.1 (ung3.2)\>|  
|GroupDate|GS04 o UNG2.4|  
|GroupTime|GS05 o UNG2.5|  
|TransactionSetId|ST01 o UNH2.1 (una cadena)|  
|InterchangeControlNo|ISA13|  
|GroupControlNo|GS06|  
|BtsDocType|NameSpace + Nombre de nodo de raíz|  
|TransactionSetControlID|ST02 o UNH1|  
|TransactionSetStatus|Aceptado, Aceptado con errores o Rechazado|  
|Dirección|Envío o Recepción|  
|BtsProcessingTime|En el lado de la recepción: BTSReceiveTime (hora local) como aparezca marcada en la canalización<br /><br /> En el lado del envío: BTSSendTime (hora local) como el componente ASM haya marcado en el sobre|  
|BTS.MessageId|En el lado de la recepción: BTSMessageId de propiedades de mensaje<br /><br /> En el lado del envío:<br /><br /> Para un único conjunto de transacciones: BTSMessageId<br /><br /> Para lotes de salida: TransactionSet BTSMessageId para cada mensaje individual en el lote (no el BTSMessageId para el mensaje de lote) **Nota:** almacenamiento solamente: no se mostrará en la interfaz de usuario.|  
  
## <a name="see-also"></a>Vea también  
 [Datos almacenados para informes de estado de AS2 y EDI](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [Datos almacenados para informes de estado de procesamiento por lotes](../core/data-stored-for-batching-status-reports.md)   
 [Datos almacenados para informes de estado de AS2](../core/data-stored-for-as2-status-reports.md)