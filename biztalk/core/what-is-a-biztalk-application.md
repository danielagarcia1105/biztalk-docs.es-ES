---
title: "¿Qué es una aplicación de BizTalk? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk.System application, about BizTalk.System application
- applications, default
- BizTalk.System application
- artifacts, about artifacts
- applications
- applications, about applications
- applications, warnings
- applications, BizTalk.System
- what's new, applications
- BizTalk.System application, warnings
ms.assetid: 68b5527c-d5e1-453b-a51b-3fc1a1d5dce2
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9ff0e2be82d528c7070955c1ce79b1f5e37cc6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-a-biztalk-application"></a>¿Qué es una aplicación de BizTalk?
La aplicación de BizTalk es una característica de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que facilita y agiliza la implementación, administración y solución de problemas de las soluciones empresariales de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Una aplicación de BizTalk es una agrupación lógica de elementos, denominados "artefactos", que se utiliza en una solución empresarial de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los artefactos se describen con más detalle posteriormente en este tema.  
  
 Las herramientas de administración y supervisión recién diseñadas de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] aprovechan este nuevo concepto, de modo que pueda administrar y configurar las soluciones empresariales de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el nivel de la aplicación y no solo en el nivel de artefactos individuales. Al crear una aplicación y agregarle artefactos, podrá ver, empaquetar, implementar y administrar un grupo de artefactos en una solución como entidad individual. Por lo tanto, aunque aumente el número de aplicaciones complejas, podrá seguir administrándolas individualmente de forma sencilla e intuitiva.  
  
 Hay varias herramientas que puede usar para crear y administrar aplicaciones, que se describen en [implementación de aplicaciones y herramientas de administración](../core/application-deployment-and-management-tools.md).  
  
 El siguiente diagrama muestra dos aplicaciones de BizTalk y los artefactos que contienen.  
  
 ![BizTalk aplicaciones y artefactos](../core/media/biztalkapplication.gif "BizTalkApplication")  
  
## <a name="artifacts"></a>Artefactos  
 Los artefactos incluyen los siguientes:  
  
-   Ensamblados de BizTalk y los recursos específicos de BizTalk que contienen: orquestaciones, canalizaciones, esquemas y asignaciones  
  
-   Ensamblados .NET que no contienen recursos específicos de BizTalk  
  
-   Directivas  
  
-   Puertos de envío, grupos de puertos de envío, ubicaciones de recepción y puertos de recepción  
  
-   Otros elementos utilizados por la solución, como certificados, componentes COM y secuencias de comandos  
  
 Para obtener información general acerca de cada tipo de artefacto, consulte [arquitectura en tiempo de ejecución](../core/runtime-architecture.md). Para obtener más información acerca de cómo agregar, quitar y configurar artefactos, vea [administrar artefactos](../core/managing-artifacts.md).  
  
 Una aplicación puede contener todos los artefactos utilizados en una solución empresarial o solo algunos. En función de cómo quiera implementarlos, puede que desee colocarlos en una sola aplicación o en dos o más aplicaciones. Para obtener más información acerca de cómo agrupar artefactos, vea [prácticas recomendadas para implementar una aplicación de BizTalk](../core/best-practices-for-deploying-a-biztalk-application.md).  
  
## <a name="the-default-application"></a>La aplicación predeterminada  
 Cuando [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se configura después de la instalación, una aplicación de forma predeterminada con nombre BizTalk Application 1 se crea automáticamente. Para obtener información sobre los procedimientos recomendados para la agrupación de artefactos en aplicaciones diferentes, consulte [prácticas recomendadas para implementar una aplicación de BizTalk](../core/best-practices-for-deploying-a-biztalk-application.md). También puede cambiar la aplicación predeterminada o cambiarle el nombre.  
  
 En los escenarios siguientes, los artefactos se agregan automáticamente a la aplicación predeterminada:  
  
-   Al implementar un ensamblado desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sin especificar el nombre de una aplicación. Para obtener más información, consulte [cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).  
  
-   Al utilizar BTSTask para agregar un artefacto a una aplicación sin especificar un nombre de aplicación. Para obtener más información, consulte [comando AddResource](../core/addresource-command.md).  
  
-   Al utilizar BTSTask para importar un archivo .msi de aplicación sin especificar un nombre de aplicación. Para obtener más información, consulte [comando ImportApp](../core/importapp-command.md).  
  
## <a name="the-biztalksystem-application"></a>La aplicación BizTalk.System  
 Cuando [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] se configura después de la instalación, una aplicación denominada BizTalk.System se crea automáticamente y se rellena con artefactos comunes utilizados por todas las aplicaciones de BizTalk, como las canalizaciones y esquemas predeterminados. BizTalk.System y sus artefactos son de solo lectura. No puede eliminar BizTalk.System ni cambiarle el nombre, así como tampoco puede eliminar, cambiar el nombre ni mover ninguno de los artefactos que contenga.  
  
> [!IMPORTANT]
>  Todas las aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contienen automáticamente una referencia a la aplicación BizTalk.System. Ello se debe a que todas las aplicaciones de BizTalk utilizan los artefactos de BizTalk.System. No debe quitar nunca las referencias a la aplicación BizTalk.System. Si lo hace, la aplicación podría no funcionar correctamente.  
  
## <a name="see-also"></a>Vea también  
 [Descripción de la implementación de aplicaciones de BizTalk y administración](../core/understanding-biztalk-application-deployment-and-management.md)