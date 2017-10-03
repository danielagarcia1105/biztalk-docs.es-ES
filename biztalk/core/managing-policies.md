---
title: Administrar directivas | Documentos de Microsoft
description: "Vínculos rápidos a importar, publicar, agregar, implementar, quitar o exportar una directiva en el servidor BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7b3bf92-8868-4c35-953f-61a7f2edff9c
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d49f0343c324900bf10c2efcce46cd57682ed04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="manage-policies"></a>Administrar directivas

## <a name="overview"></a>Información general
Los temas de esta sección proporcionan instrucciones sobre el uso de la consola de administración de BizTalk Server o la herramienta de línea de comandos BTSTask para administrar directivas. Una directiva es una agrupación lógica de reglas de negocios. Para obtener información general sobre las directivas, consulte [directivas](../core/policies.md).  
  
## <a name="import-publish-deploy-and-remove-policies"></a>Importar, publicar, implementar y quitar directivas
 Los programadores de soluciones pueden crear y ver directivas mediante el Compositor de reglas de negocios, como se describe en [crear reglas de negocios mediante el Compositor de reglas de negocios](../core/creating-business-rules-using-the-business-rule-composer.md). Posteriormente, los programadores y administradores de TI pueden realizar las tareas que se describen en los temas de esta sección para implementar y administrar las directivas en un grupo y una aplicación de BizTalk:  
  
-   **Importar la directiva a un grupo de BizTalk.** Al hacerlo, la directiva se agrega a la base de datos de motor de reglas para el grupo y se muestra en la consola de administración de BizTalk Server en la \<todos los artefactos > nodo para el grupo de BizTalk. Con esta acción, la directiva no se activa para ninguna aplicación concreta. En primer lugar, debe publicar la directiva, luego agregarla a una aplicación y, por último, implementarla, como se describe en otros temas de esta sección. La base de datos del motor de reglas es una base de datos que contiene todas las directivas de un grupo de BizTalk Server.  
  
-   **Publicar una directiva.** al publicarse, la directiva está disponible para su uso en una aplicación de BizTalk.  
  
-   **Agregar una directiva a una aplicación de BizTalk.** esto permite a la aplicación usar la directiva, pero la directiva no entra en vigor. La directiva entra en vigor cuando se implementa.  
  
    > [!IMPORTANT]
    >  Si una directiva se comparte entre dos o más aplicaciones, debe crear una aplicación diferente para que la contenga y, a continuación, crear referencias a la aplicación que contiene la directiva desde las aplicaciones que la usan. Esto es necesario porque al detener una aplicación que contiene una directiva, la implementación de la misma se anula automáticamente y la directiva deja de funcionar para cualquiera de las aplicaciones que la usen.  
  
-   **Implementar una directiva.** con esto, se activa el mecanismo de la directiva. (Es similar a iniciar a una orquestación). La implementación y anulación de la implementación de una directiva se puede realizar manualmente. Además, al iniciar una aplicación, las directivas correspondientes se implementan automáticamente, y cuando se detiene, se anula de forma automáticamente su implementación.  
  
    > [!NOTE]
    >  Las directivas, una vez implementadas, no se pueden modificar. Si desea modificar una directiva implementada, debe anular su implementación o volver a crearla con el Compositor de reglas de negocio y asignarle un número de versión nuevo.  
  
-   **Quitar una directiva de una aplicación de BizTalk y el grupo de BizTalk.** con esta acción, se anula la implementación de la directiva; asimismo, la directiva se quita de la aplicación y de la base de datos del motor de reglas para el grupo.  
  
-   **Exportar la directiva.** posteriormente, puede importarla a un grupo de BizTalk distinto para usarla allí.  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Importar una directiva](../core/how-to-import-a-policy.md)  
  
-   [Publicar una directiva](../core/how-to-publish-a-policy.md)  
  
-   [Agregar una directiva a una aplicación](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [Implementar o anular la implementación de una directiva](../core/how-to-deploy-or-undeploy-a-policy.md)  
  
-   [Configurar el seguimiento de una directiva](../core/how-to-configure-tracking-for-a-policy.md)  
  
-   [Quitar una directiva de una aplicación y el grupo de BizTalk](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [Exportar una directiva](../core/how-to-export-a-policy.md)