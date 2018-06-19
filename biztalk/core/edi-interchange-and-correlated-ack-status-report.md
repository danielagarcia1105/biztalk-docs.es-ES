---
title: Intercambio EDI y el informe de estado de confirmación correlacionado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a112cc3d-d34c-4652-a8ee-3355a31d4a03
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd5f4268badf9907eb90b090abe34a8355b3ab8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242372"
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a>Informe Intercambio EDI y estado de confirmación correlacionado
Este informe muestra todos los intercambios EDI procesados por las canalizaciones de envío y recepción EDI, así como la confirmación correlacionada con dichos intercambios.  
  
## <a name="fields-in-the-status-report"></a>Campos del informe de estado  
 El informe Intercambio EDI y estado de confirmación correlacionado muestra la siguiente información relativa a los intercambios enviados o recibidos y a las confirmaciones correlacionadas.  
  
-   Entidad del remitente.  
  
    > [!NOTE]
    >  La entidad del remitente se determinará de la forma siguiente:  
    >   
    >  -   Si el nombre de la entidad del intercambio coincide con el nombre configurado en las propiedades de EDI para un entidad, se muestra el nombre configurado.  
    > -   Si el nombre de la entidad del intercambio no coincide con ninguna de las propiedades de EDI configuradas para las entidades existentes, se muestra el nombre de la entidad especificada en el intercambio.  
  
-   Entidad receptora  
  
    > [!NOTE]
    >  El nombre de la entidad receptora se determinará de la forma siguiente:  
    >   
    >  -   Si el nombre de la entidad del intercambio coincide con el nombre configurado en las propiedades de EDI para un entidad, se muestra el nombre configurado.  
    > -   Si el nombre de la entidad del intercambio no coincide con ninguna de las propiedades de EDI configuradas para las entidades existentes, se muestra el nombre de la entidad especificada en el intercambio.  
  
-   Id. de control  
  
-   Dirección  
  
-   Fecha y hora de intercambio  
  
-   Tipo de codificación EDI  
  
-   Estado del intercambio  
  
-   Recuento de grupo  
  
-   Id. de puerto  
  
-   Alias de entidad remitente  
  
-   Alias de entidad receptora  
  
-   Identificador de correlación del conjunto de transacciones  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>Campos de Expresión de consulta para el informe de estado  
 Para personalizar el informe Intercambio EDI y estado de confirmación correlacionado, cambie los campos de la expresión de consulta que determina los datos que se muestran. Están disponibles los campos siguientes:  
  
|||||  
|-|-|-|-|  
|Campo Expresión de consulta|Operadores potenciales|Valores potenciales|¿Incluido de forma predeterminada?|  
|Buscar|Es igual a|Estado de la confirmación y del intercambio|Sí (obligatorio)|  
|Estado|Es igual a<br /><br /> No es igual a|Aceptado<br /><br /> Aceptado con errores<br /><br /> Enviado<br /><br /> Todos<br /><br /> Confirmación esperada<br /><br /> Confirmación inesperada<br /><br /> Rechazado<br /><br /> (Estos valores se definen a continuación.)|Sí|  
|Fecha y hora de intercambio|Menor o igual que<br /><br /> Mayor o igual que|Fecha y hora específica<br /><br /> Hoy<br /><br /> Hoy - 1|Sí<br /><br /> Nota: se puede incluir más de una vez en la expresión de consulta.|  
|N.º máximo de coincidencias|Es igual a|Entero (predeterminado de 50)|Sí|  
|Id. de control|Es igual a|Id. de control de intercambio|No|  
|Dirección|Es igual a|All (valor predeterminado)<br /><br /> Receive<br /><br /> Send|No|  
|Entidad receptora|Es igual a|All (valor predeterminado)<br /><br /> Nombre de entidad específico|No|  
|Entidad del remitente.|Es igual a|All (valor predeterminado)<br /><br /> Nombre de entidad específico|No|  
  
## <a name="status-definitions"></a>Definiciones de estado  
 Los valores de estado empleados en los informes de estado EDI tienen las definiciones siguientes:  
  
-   Aceptado: intercambio válido  
  
-   Aceptado con errores: se han registrado los errores en los segmentos  
  
-   Enviado: el intercambio se envió correctamente  
  
-   Todo: mostrar un mensaje con cualquiera de los demás valores  
  
-   Confirmación esperada  
  
    > [!NOTE]
    >  El campo Estado de intercambio del informe de estado Detalles de la confirmación y del estado del intercambio se establecerá como "Confirmación esperada" para un mensaje saliente al enviarlo si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] espera una confirmación técnica. Esto ocurre si el **TA1 esperado** propiedad se establece en **confirmaciones** página de la ficha de acuerdo unidireccional. El estado cambiará a "Aceptado" cuando se haya recibido y validado la confirmación técnica. Tenga en cuenta que esto solo sucede en el caso de una confirmación técnica, no de una confirmación funcional.  
  
-   Confirmación inesperada  
  
-   Rechazado: el intercambio no era válido debido a los errores.  
  
## <a name="additional-reports-displayed-from-this-report"></a>Otros informes mostrados desde este informe  
 Puede mostrar los siguientes informes de estado adicionales para un conjunto de transacciones mostrado en el informe Detalles de conjunto de transacciones: Para obtener acceso a los informes, haga clic con el botón secundario en un intercambio o una confirmación enumerados en el informe Intercambio EDI y estado de confirmación correlacionado y, a continuación, haga clic en el comando adecuado:  
  
-   [Estado de intercambio y el informe de estado de detalles de confirmación](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [Informe de estado de detalles de conjunto de transacciones](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Estado de intercambio y el informe de estado de detalles de confirmación](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [Informe de estado de detalles de conjunto de transacciones](../core/transaction-set-details-status-report.md)  
  
-   [Informe de estado del contenido del mensaje EDI](../core/edi-message-content-status-report.md)  
  
