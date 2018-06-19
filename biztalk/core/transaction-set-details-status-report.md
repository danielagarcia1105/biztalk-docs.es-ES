---
title: Informe de estado de detalles de conjunto de transacciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d81367c7-c74e-42cb-b856-748962b727ec
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6da167ea995fa05d8e35807d8cf26f23b5444a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279516"
---
# <a name="transaction-set-details-status-report"></a>Informe de estado de detalles del conjunto de transacciones
Este informe muestra los detalles de conjuntos de transacciones en un intercambio EDI seleccionado desde el informe Estado de la confirmación y del intercambio. Para mostrar este informe de estado, haga clic en un intercambio mostrado en el panel de resultados de consulta del informe de estado de confirmación y del intercambio y, a continuación, haga clic en **detalles de conjunto de transacciones**.  
  
 Este informe solo está disponible si ha seleccionado la **almacenar carga y conjunto de transacciones para los informes** propiedad en la página General del cuadro de diálogo Propiedades de EDI de la entidad relacionada.  
  
## <a name="fields-in-the-status-report"></a>Campos del informe de estado  
 El informe de estado de detalles del conjunto de transacciones muestra la siguiente información correspondiente a los conjuntos de transacciones en intercambios recibidos o enviados:  
  
-   Id. de conjunto de transacciones  
  
-   Tipo de documento  
  
-   Alias de entidad remitente  
  
-   Remitente de aplicación  
  
-   Alias de entidad receptora  
  
-   Receptor de aplicación  
  
-   Dirección  
  
-   Número de Control de intercambio  
  
-   Número de control de grupo  
  
-   Número de control del conjunto de transacciones  
  
-   Estado de conjunto de transacciones  
  
-   Fecha y hora de intercambio (no se muestra de forma predeterminada)  
  
    > [!NOTE]
    >  Para los documentos recibidos, si la fecha especificada en el intercambio se encuentra en formato AAMMDD y AA es mayor o igual a 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mostrará el año como 19AA. Si la fecha es inferior a 75, se mostrará como 20AA.  
    >   
    >  Por ejemplo, si recibe un intercambio que contiene el valor 991113 en ISA09, la fecha y hora de intercambio se indicará en el informe como 11/13/1999.  
  
-   Fecha y hora de procesamiento (no se muestra de forma predeterminada)  
  
-   Fecha y hora de grupo (no se muestra de forma predeterminada)  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>Campos de Expresión de consulta para el informe de estado  
 Para personalizar el informe Intercambio EDI y estado de confirmación correlacionado, cambie los campos de la expresión de consulta que determina los datos que se muestran. Están disponibles los campos siguientes:  
  
|||||  
|-|-|-|-|  
|Campo Expresión de consulta|Operadores potenciales|Valores potenciales|¿Incluido de forma predeterminada?|  
|Buscar|Es igual a|Detalles de conjunto de transacciones|Sí (obligatorio)|  
|Fecha y hora de intercambio|Menor o igual que<br /><br /> Mayor o igual que|Fecha y hora específica<br /><br /> Hoy<br /><br /> Hoy - 1|Sí<br /><br /> Nota: se puede incluir más de una vez en la expresión de consulta.|  
|Nombre de la entidad receptora|Es igual a|All (valor predeterminado)<br /><br /> Nombre de entidad específico|Sí|  
|Nombre de la entidad remitente|Es igual a|All (valor predeterminado)<br /><br /> Nombre de entidad específico|Sí|  
|Dirección|Es igual a|All (valor predeterminado)<br /><br /> Receive<br /><br /> Send|Sí|  
|Id. de control|Es igual a|Id. de control de intercambio|Sí|  
|Id. de correlación del conjunto de transacciones|Es igual a|Id. de correlación|Sí|  
|N.º máximo de coincidencias|Es igual a|Entero (predeterminado de 50)|Sí|  
|Estado|Es igual a<br /><br /> No es igual a|Aceptado<br /><br /> Aceptado con errores<br /><br /> Enviado<br /><br /> Todos<br /><br /> Confirmación esperada<br /><br /> Confirmación inesperada<br /><br /> Rechazado|No|  
|Identificador de conjunto de transacciones|Es igual a|Identificador de conjunto de transacciones|No|  
  
## <a name="additional-reports-displayed-from-this-report"></a>Otros informes mostrados desde este informe  
 Puede mostrar los siguientes informes de estado adicionales para un conjunto de transacciones mostrado en el informe de detalles del conjunto de transacciones:  
  
-   Informe de estado Contenido de mensaje. Puede obtener acceso a este informe haciendo clic con el botón secundario en un conjunto de transacciones en los informes de detalles y, a continuación, haciendo clic en Ver contenido de conjunto de transacciones. Para obtener más información, consulte [informe de estado de contenido de mensaje de EDI](../core/edi-message-content-status-report.md).  
  
-   Informe Estado de la confirmación y del intercambio. Este informe utiliza la misma interfaz de usuario como la [intercambio EDI y el informe de estado de confirmación correlacionado](../core/edi-interchange-and-correlated-ack-status-report.md) que se muestra para varios intercambios. La diferencia está en que los datos de este informe se refieren sólo al intercambio que contiene este conjunto de transacciones.  
  
