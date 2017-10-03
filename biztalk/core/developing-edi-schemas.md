---
title: Desarrollo de esquemas EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a8fbf3d-ebc7-47f6-87fa-e45722651262
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b241b5d0477d7aa477511c43b642e4e312f2651a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="developing-edi-schemas"></a>Desarrollar esquemas EDI
En los temas de esta sección se describe cómo modificar los esquemas EDI para su uso con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Para usar un esquema de documento en la solución, debe implementar el esquema al agregarlo a un proyecto de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. A continuación, debe crear e implementar el proyecto. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]implementará el proyecto en el valor predeterminado 1 de aplicación de BizTalk. Puede ver los esquemas que se implementan abriendo el **esquemas** nodo bajo **BizTalk Application 1** nodo el **aplicaciones** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Consola de administración. Puede implementar un ensamblado en una aplicación diferente mediante la herramienta de implementación de línea de comandos `BTSTask`.  
  
 El Asistente para configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementa automáticamente los esquemas de control y servicio. Para verlos, haga clic en el **esquemas** nodo en el **aplicación EDI de BizTalk** nodo en la consola de administración. Para obtener más información acerca de estos esquemas, vea [servicio EDI y esquemas de Control](../core/edi-service-and-control-schemas.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Modificación de esquemas EDI](../core/modifying-edi-schemas.md)  
  
-   [Personalizar enumeraciones en el esquema de sobres](../core/customizing-enumerations-in-the-envelope-schema.md)  
  
-   [Configuración de la validación de campos cruzados](../core/configuring-cross-field-validation.md)  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md)