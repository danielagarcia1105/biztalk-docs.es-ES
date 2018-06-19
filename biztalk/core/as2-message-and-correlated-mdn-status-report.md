---
title: AS2 Mensaje y el informe de estado MDN correlacionado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48ed0ee3-c844-4cb9-a84d-32b719ab8fab
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ce4aed138f4e32e87cb1d428050999cc2b764a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232980"
---
# <a name="as2-message-and-correlated-mdn-status-report"></a>Informe de mensaje AS2 y estado de MDN correlacionado
Este informe muestra todos los mensajes AS2 procesados por las canalizaciones de envío y recepción AS2, así como los MDN correlacionados con dichos intercambios.  
  
## <a name="fields-in-the-status-report"></a>Campos del informe de estado  
 El informe de mensaje AS2 y estado de confirmación correlacionado muestra la siguiente información relativa a los intercambios enviados o recibidos y a las confirmaciones correlacionadas:  
  
-   Nombre de la entidad remitente  
  
-   Nombre de la entidad receptora  
  
-   AS2 From  
  
-   AS2 To  
  
-   Id. de mensaje AS2  
  
-   Fecha y hora del mensaje AS2  
  
-   Fecha y hora de recepción  
  
-   Función de entidad  
  
-   Estado de MDN  
  
-   Estado de cifrado  
  
-   Estado de firma  
  
-   Estado de intercambio EDI  
  
-   Es el mensaje AS2 duplicado  
  
-   Días para comprobar si hay duplicados  
  
-   Nombre de archivo  
  
-   Mensajería confiable habilitada  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>Campos de Expresión de consulta para el informe de estado  
 Para personalizar el informe de mensaje AS2 y estado de confirmación correlacionado, cambie los campos de la expresión de consulta que determina los datos que se muestran. Están disponibles los campos siguientes:  
  
|||||  
|-|-|-|-|  
|Campo Expresión de consulta|Operadores potenciales|Valores potenciales|¿Incluido de forma predeterminada?|  
|Buscar|Es igual a|Estado de AS2 y MDN|Sí (obligatorio)|  
|Estado de mensaje|Es igual a<br /><br /> No es igual a|Todos<br /><br /> Confirmado - Procesado<br /><br /> Confirmado - Error<br /><br /> Procesado - MDN pendiente<br /><br /> Procesado - MDN no esperado<br /><br /> No confirmado - Intentos de reenvío superados<br /><br /> No confirmado - Duración de reenvío superada|Sí|  
|Fecha y hora del mensaje AS2|Menor o igual que<br /><br /> Mayor o igual que|Fecha y hora específica<br /><br /> Hoy<br /><br /> Hoy - 1|Sí<br /><br /> Nota: se puede incluir más de una vez en la expresión de consulta.|  
|N.º máximo de coincidencias|Es igual a|Entero (predeterminado de 50)|Sí|  
|Id. de mensaje AS2|Es igual a|Todos<br /><br /> Id. de mensaje AS2 específico|No|  
|Dirección|Es igual a|All (valor predeterminado)<br /><br /> Receive<br /><br /> Send|No|  
|Nombre de la entidad receptora|Es igual a|All (valor predeterminado)<br /><br /> Nombre de entidad específico|No|  
|Nombre de la entidad remitente|Es igual a|All (valor predeterminado)<br /><br /> Nombre de entidad específico|No|  
  
## <a name="additional-as2-message-and-correlated-mdn-status-reports"></a>Informes de mensaje AS2 y estado de MDN correlacionado  
 Si hace clic con el botón secundario en un mensaje AS2 enumerado en el informe de mensaje AS2 y estado de MDN correlacionado, podrá mostrar uno de los siguientes informes de estado que se encuentran más detallados:  
  
|Informe de estado|Estado mostrado|  
|-------------------|----------------------|  
|Estado de la confirmación y del intercambio|El estado de la carga EDI del mensaje AS2|  
|Detalles del estado de reenvío|El estado de reenvío del mensaje|  
|Formato de mensaje|El formato de mensaje del mensaje AS2|  
|Mensaje descodificado|El formato con descodificación del mensaje AS2|  
|Mensaje MDN|El mensaje MDN correlacionado con el mensaje de AS2|  
  
 El formato de los últimos tres mensajes es el mismo. Para obtener más información, consulte [informes de estado de contenido de mensaje de AS2](../core/as2-message-content-status-reports.md).  
  
## <a name="correlate-an-as2-message-with-its-edi-payload"></a>Correlacionar un mensaje AS2 con su carga EDI.  
 La creación de informes de estado EDI y AS2 le permite correlacionar entradas de estado para un mensaje AS2 y para su carga EDI. Si ha habilitado la creación de informes de estado EDI y AS2, se creará una entrada de estado en el informe de estado de AS2 para el mensaje AS2 y, por otro lado, se creará una entrada de estado en el informe de estado EDI para la carga EDI de ese mensaje AS2. Si tienes que muestra el informe de estado de AS2, puede mostrar el estado de la carga EDI para un mensaje AS2 haciendo clic en la entrada de estado de mensaje de AS2 y, a continuación, haga clic en **estado de confirmación y del intercambio**. Si sólo hay un intercambio EDI en el mensaje AS2, esta acción mostrará la entrada de estado para ese único intercambio.  
  
 Si el mensaje AS2 contiene varios intercambios EDI e intenta mostrar el estado de varios intercambios EDI del mensaje AS2, sólo el último intercambio EDI se mostrará en el informe de estado de la confirmación y del intercambio. Además, el **n de Control de intercambio de EDI** campo en el informe de estado de AS2 y MDN sólo mostrará el último número de control de intercambio. (El número de control de intercambio correlaciona el mensaje AS2 y su carga de intercambio EDI).  
  
 Los datos para todos los intercambios EDI en un mensaje AS2 se guardan en la base de datos de informe de estado. Puede mostrar todos los intercambios en un mensaje de AS2 en el informe de estado de confirmación y del intercambio si la **Control Id. es igual a todos** cláusula está en la consulta de informe de estado. Esto también puede hacer que se muestren otros intercambios que no se encuentren en el mensaje AS2, sin embargo, puede determinar los intercambios EDI que son en un único mensaje AS2 si busca en otros campos, como en Entidad remitente, Entidad receptora y Fecha y hora de intercambio.  
  
 El **función de entidad** campo en el informe de estado de AS2 y **dirección** campo en el informe de estado EDI son opuesto en su significado. Para un mensaje AS2 entrante con una carga EDI, el **función de entidad** campo para el mensaje AS2 sería **remitente**, mientras que la **dirección** campo para el intercambio EDI sería **Recibir**. Esto se debe a que para un mensaje entrante recibido desde una entidad, la función de esta entidad es de remitente. Las propiedades de esa entidad relacionada con un mensaje AS2 que ésta envía son las de una entidad remitente del mensaje AS2, tal y como se define en el cuadro de diálogo Propiedades de AS2 de la Administración de acuerdos de socios comerciales. Como consecuencia, la función de entidad AS2 se opone a la dirección de EDI.  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [AS2 Informes de estado del contenido del mensaje](../core/as2-message-content-status-reports.md)  
  
-   [Enviar informe de detalles de estado](../core/resend-status-details-report.md)  
  
## <a name="see-also"></a>Vea también  
 [AS2 Mensaje y el informe de estado MDN correlacionado](../core/as2-message-and-correlated-mdn-status-report.md)   
