---
title: ¿Qué es una aplicación de BizTalk? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68e01881693c7db8b12b7da4edf246942fe02825
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008781"
---
# <a name="what-is-a-biztalk-application"></a>¿Qué es una aplicación de BizTalk?
La aplicación de BizTalk es una característica de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que facilita y agiliza la implementación, administración y solución de problemas de las soluciones empresariales de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Una aplicación de BizTalk es una agrupación lógica de elementos, denominados "artefactos", que se utiliza en una solución empresarial de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los artefactos se describen con más detalle posteriormente en este tema.  
  
 La administración recién diseñada y herramientas de BizTalk Server de supervisión aprovechan las ventajas de este nuevo concepto, para que pueda administrar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solutions en el nivel de aplicación y no solo en el nivel de artefactos individuales. Al crear una aplicación y agregarle artefactos, podrá ver, empaquetar, implementar y administrar un grupo de artefactos en una solución como entidad individual. Por lo tanto, aunque aumente el número de aplicaciones complejas, podrá seguir administrándolas individualmente de forma sencilla e intuitiva.  
  
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
 Cuando BizTalk Server se configura después de la instalación, se crea automáticamente una aplicación predeterminada denominada BizTalk Application 1. Para obtener información sobre los procedimientos recomendados para la agrupación de artefactos en aplicaciones diferentes, consulte [prácticas recomendadas para implementar una aplicación de BizTalk](../core/best-practices-for-deploying-a-biztalk-application.md). También puede cambiar la aplicación predeterminada o cambiarle el nombre.  
  
 En los escenarios siguientes, los artefactos se agregan automáticamente a la aplicación predeterminada:  
  
-   Al implementar un ensamblado desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sin especificar el nombre de una aplicación. Para obtener más información, consulte [cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).  
  
-   Al utilizar BTSTask para agregar un artefacto a una aplicación sin especificar un nombre de aplicación. Para obtener más información, consulte [comando AddResource](../core/addresource-command.md).  
  
-   Al utilizar BTSTask para importar un archivo .msi de aplicación sin especificar un nombre de aplicación. Para obtener más información, consulte [comando ImportApp](../core/importapp-command.md).  
  
## <a name="the-biztalksystem-application"></a>La aplicación BizTalk.System  
 Cuando BizTalk Server está configurado después de la instalación, se crea automáticamente una aplicación denominada BizTalk.System y se rellena con artefactos comunes utilizados por todas las aplicaciones de BizTalk, como las canalizaciones y esquemas predeterminados. BizTalk.System y sus artefactos son de solo lectura. No puede eliminar BizTalk.System ni cambiarle el nombre, así como tampoco puede eliminar, cambiar el nombre ni mover ninguno de los artefactos que contenga.  
  
> [!IMPORTANT]
>  Todas las aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contienen automáticamente una referencia a la aplicación BizTalk.System. Ello se debe a que todas las aplicaciones de BizTalk utilizan los artefactos de BizTalk.System. No debe quitar nunca las referencias a la aplicación BizTalk.System. Si lo hace, la aplicación podría no funcionar correctamente.  
  
## <a name="see-also"></a>Vea también  
 [Descripción de la implementación y administración de aplicaciones de BizTalk](../core/understanding-biztalk-application-deployment-and-management.md)