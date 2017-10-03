---
title: "Configuración de EDI y AS2 de informes de estado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c7fa76d-0d03-4b74-9a3a-60f4bd0534ff
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051a03b735f3714910b415d5418ff84089c57940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-of-edi-and-as2-status-reporting"></a>Configuración del informe de estado de EDI y AS2
En este tema se describe la habilitación del informe de estado de EDI y AS2 y la configuración de los filtros de informes de estado y muestran columnas de EDI, procesamiento por lotes e informes de estado de AS2.  
  
## <a name="enabling-status-reporting"></a>Habilitar informes de estado  
 Los informes de estado de EDI solo están disponibles en un servidor si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con los subsistemas de BAM y EDI están instalados en dicho servidor. Los informes de estado de EDI o AS2 no se pueden habilitar si no está instalada la infraestructura de BAM. El servidor debe también ser un miembro del grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de procesamiento de EDI para que tenga acceso al almacenamiento de datos de informes de estado de EDI.  
  
 Las entradas de mensajes EDI se especificarán para intercambios de entidades en el informe de estado de interfaz de usuario si la **activar informes** propiedad está seleccionada en el **propiedades generales** página de la **General** pestaña en el **propiedades del acuerdo de** cuadro de diálogo. Si la entidad que envía o recibe intercambios no está determinada, las entradas de mensajes EDI se especificarán para los intercambios sólo si la **activar informes de EDI** propiedad está seleccionada en el acuerdo de reserva para X12 y EDIFACT. Esto se aplica al informe de estado de confirmación correlacionado y de intercambio de EDI. El informe de estado del lote solo se habilita si se ha determinado un acuerdo y el **activar informes** propiedad está seleccionada en **propiedades generales** página de la **General** pestaña en el **propiedades del acuerdo de** cuadro de diálogo.  
  
 Conjuntos de transacciones se almacenarán en la base de datos de seguimiento si el **almacenar carga de mensaje para informes** propiedad está seleccionada en **propiedades generales** página de la **General** pestaña en el **propiedades del acuerdo de** cuadro de diálogo o **almacenar carga y conjunto de transacciones para los informes** propiedad está establecida en las propiedades del acuerdo de reserva. Los informes de estado de los detalles de la transacción y el contenido del mensaje solo estarán disponibles si se selecciona esta propiedad.  
  
 Las entradas de mensajes de AS2 se especificarán en el informe de estado de interfaz de usuario si la **activar informes** propiedad está seleccionada en el **propiedades generales** página de la **General** ficha en el  **Propiedades del acuerdo de** cuadro de diálogo. Para almacenar el mensaje AS2 o MDN en la base de datos sin repudio, debe seleccionar la propiedad adecuada en la **sin repudio de remitente** o **sin repudio de receptor** páginas del acuerdo AS2 unidireccional pestaña en el **propiedades del acuerdo de** cuadro de diálogo. Estas propiedades habilitan el informe de estado MDN correlacionado y el de mensaje AS2.  
  
 El informe de estado de mensajería confiable estará disponible si la **reenviar mensaje AS2 si no se recibe MDN** propiedad está habilitada en **configuración de MDN de remitente** página de la ficha de acuerdo AS2 unidireccional del **Propiedades de acuerdo** cuadro de diálogo.  
  
 Para obtener más información acerca de cómo habilitar los informes de estado, consulte [habilitar informes de EDI y AS2 estado](../core/enabling-edi-and-as2-status-reports.md).  
  
## <a name="status-report-filters-and-display-columns"></a>Filtros de informes de estado y visualización de columnas  
 Los informes de estado EDI y AS2 le permiten personalizar el intervalo de los datos que se guardan para el informe de estado. Hacer esto en el **concentrador de grupo** página de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Una vez que haya visualizado el panel del informe de estado para cualquier informe, puede seleccionar el intervalo de datos que desea ver en el informe. Puede hacer esto seleccionando los valores de filtro para incluir la expresión de consulta del informe de estado.  
  
 También puede personalizar el tipo de datos que se visualiza en el informe de estado.  
  
> [!NOTE]
>  Siempre que el informe de estado esté habilitado, todos los estados se guardarán en su ubicación. Mediante la personalización de la expresión de consulta o columnas de estado, se definen los datos guardados que se visualizan.  
  
 Para obtener más información, consulte [configurar un informe de estado de AS2 y EDI](../core/configuring-an-edi-and-as2-status-report.md).  
  
## <a name="see-also"></a>Vea también  
 [EDI y AS2 informes de estado](../core/edi-and-as2-status-reporting.md)   
 [Intercambio EDI y el informe de estado de confirmación correlacionado](../core/edi-interchange-and-correlated-ack-status-report.md)   
 [Informe de estado](../core/batch-status-report.md)   
 [Informe de agregación de intercambio](../core/interchange-aggregation-report.md)   
 [Informe de agregación de conjunto de transacciones](../core/transaction-set-aggregation-report.md)   
 [AS2 Mensaje y el informe de estado MDN correlacionado](../core/as2-message-and-correlated-mdn-status-report.md)